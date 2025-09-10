# Домашнее задание к занятию "Кластеризация и балансировка нагрузки" - Коноплёв Александр


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

Запустите два simple python сервера на своей виртуальной машине на разных портах
Установите и настройте HAProxy, воспользуйтесь материалами к лекции по ссылке
Настройте балансировку Round-robin на 4 уровне.
На проверку направьте конфигурационный файл haproxy, скриншоты, где видно перенаправление запросов на разные серверы при обращении к HAProxy.

# 1. Обновление системы и установка необходимых пакетов

# Обновление пакетов
sudo apt update
sudo apt upgrade -y

# Установка Python3 и pip
sudo apt install python3 python3-pip -y

# Установка HAProxy
sudo apt install haproxy -y

# Установка net-tools для проверки портов
sudo apt install net-tools -y

# 2. Создание Python серверов

# Создайте server1.py:

import http.server
import socketserver

PORT = 8001

class MyHandler(http.server.SimpleHTTPRequestHandler):
    def do_GET(self):
        self.send_response(200)
        self.send_header('Content-type', 'text/html')
        self.end_headers()
        response = f"Hello from Server 1 on port {PORT}"
        self.wfile.write(response.encode())
        print(f"Request served by Server 1 (port {PORT})")

with socketserver.TCPServer(("", PORT), MyHandler) as httpd:
    print(f"Server 1 started on port {PORT}")
    httpd.serve_forever()

# 3. Создайте server2.py:

nano server2.py

import http.server
import socketserver

PORT = 8002

class MyHandler(http.server.SimpleHTTPRequestHandler):
    def do_GET(self):
        self.send_response(200)
        self.send_header('Content-type', 'text/html')
        self.end_headers()
        response = f"Hello from Server 2 on port {PORT}"
        self.wfile.write(response.encode())
        print(f"Request served by Server 2 (port {PORT})")

with socketserver.TCPServer(("", PORT), MyHandler) as httpd:
    print(f"Server 2 started on port {PORT}")
    httpd.serve_forever()

# 4. Запуск серверов в фоновом режиме

# Запуск серверов в фоне
python3 server1.py &
SERVER1_PID=$!
python3 server2.py &
SERVER2_PID=$!

# Сохранить PID для последующего завершения
echo "Server PIDs: $SERVER1_PID, $SERVER2_PID"

# 5. Проверка работы серверов

curl http://localhost:8001
curl http://localhost:8002

# 6. Настройка HAProxy

sudo cp /etc/haproxy/haproxy.cfg /etc/haproxy/haproxy.cfg.backup
sudo nano /etc/haproxy/haproxy.cfg

global
    log /dev/log    local0
    log /dev/log    local1 notice
    chroot /var/lib/haproxy
    stats socket /run/haproxy/admin.sock mode 660 level admin expose-fd listeners
    stats timeout 30s
    user haproxy
    group haproxy
    daemon

defaults
    log     global
    mode    tcp
    option  tcplog
    option  dontlognull
    timeout connect 5000
    timeout client  50000
    timeout server  50000

frontend http_front
    bind *:80
    default_backend http_back

backend http_back
    balance roundrobin
    server server1 127.0.0.1:8001 check
    server server2 127.0.0.1:8002 check

listen stats
    bind *:1936
    stats enable
    stats uri /
    stats hide-version
    stats auth admin:password

# 7. Запуск HAProxy
sudo systemctl restart haproxy
sudo systemctl enable haproxy

# 8. Тестирование задания

echo "=== Testing Round Robin (5 requests) ==="
for i in {1..5}; do
    echo "Request $i: $(curl -s http://localhost)"
    sleep 1
done

# Проверка балансировки нагрузки серверов (Скриншот 1)
<img width="944" height="436" alt="Балансировка нагрузки" src="https://github.com/user-attachments/assets/b939e90d-90ca-4325-ad9e-63a1ddc5bba6" />
# Проверка работы серверов (Скриншот 2)
<img width="905" height="148" alt="Проверка работы серверов" src="https://github.com/user-attachments/assets/bbc08b32-8ccd-46b3-9b99-e6c9e57e9d9d" />

# Задание 2
Запустите три simple python сервера на своей виртуальной машине на разных портах
Настройте балансировку Weighted Round Robin на 7 уровне, чтобы первый сервер имел вес 2, второй - 3, а третий - 4
HAproxy должен балансировать только тот http-трафик, который адресован домену example.local
На проверку направьте конфигурационный файл haproxy, скриншоты, где видно перенаправление запросов на разные серверы при обращении к HAProxy c использованием домена example.local и без него.

# 1. Создание третьего сервера

# server3.py:

nano server3.py

import http.server
import socketserver
import time

PORT = 8003

class MyHandler(http.server.SimpleHTTPRequestHandler):
    def do_GET(self):
        self.send_response(200)
        self.send_header('Content-type', 'text/html')
        self.end_headers()
        response = f"Hello from Server 3 on port {PORT} - {time.time()}"
        self.wfile.write(response.encode())
        print(f"Request served by Server 3 (port {PORT})")

print(f"Starting Server 3 on port {PORT}")
with socketserver.TCPServer(("", PORT), MyHandler) as httpd:
    httpd.serve_forever()

# 2. Запуск третьего сервера

python3 server3.py &
SERVER3_PID=$!
echo "Server3 PID: $SERVER3_PID"

# 3. Настройка hosts файла

echo "127.0.0.1 example.local" | sudo tee -a /etc/hosts

# 4. Обновление конфига HAProxy

sudo nano /etc/haproxy/haproxy.cfg

global
    log /dev/log    local0
    log /dev/log    local1 notice
    chroot /var/lib/haproxy
    stats socket /run/haproxy/admin.sock mode 660 level admin expose-fd listeners
    stats timeout 30s
    user haproxy
    group haproxy
    daemon

defaults
    log     global
    mode    http
    option  httplog
    option  dontlognull
    timeout connect 5000
    timeout client  50000
    timeout server  50000

frontend http_front
    bind *:80
    acl is_example_local hdr(host) -i example.local
    use_backend weighted_back if is_example_local
    default_backend default_back

backend weighted_back
    balance roundrobin
    server server1 127.0.0.1:8001 weight 2 check
    server server2 127.0.0.1:8002 weight 3 check
    server server3 127.0.0.1:8003 weight 4 check

backend default_back
    server default_server 127.0.0.1:8001 check

listen stats
    bind *:1936
    stats enable
    stats uri /
    stats hide-version
    stats auth admin:password

# 5. Тестирование задания 

С доменом (weighted round robin):

echo "=== Testing Weighted Round Robin with example.local (15 requests) ==="
for i in {1..15}; do
    echo "Request $i: $(curl -s -H "Host: example.local" http://localhost)"
    sleep 0.3
done
Тестирование работы с доменом (Скриншот 3)
<img width="947" height="915" alt="Балансировка2" src="https://github.com/user-attachments/assets/5da8a1c2-5f0f-4563-acd3-ca9cbf9db16a" />

Без домена (только server1):

echo "=== Testing without domain (5 requests) ==="
for i in {1..5}; do
    echo "Request $i: $(curl -s http://localhost)"
    sleep 0.5
done

Тестирование работы без домена (Скриншот 4)
<img width="767" height="364" alt="Без домена" src="https://github.com/user-attachments/assets/dd3a2d0d-d3f6-4332-abc1-bfa520f0c635" />

Проверка статистики

echo "=== HAProxy Stats ==="
echo "Open in browser: http://localhost:1936"
echo "Login: admin"
echo "Password: password"

Проверка статистики (Скриншот 5)
<img width="588" height="160" alt="проверка статистики" src="https://github.com/user-attachments/assets/17897de4-5380-450e-adfa-157de91d8060" />

Посмотреть работающие серверы:
ps aux | grep "python3 server"

Проверка работы серверов (Скриншот 6)
<img width="807" height="111" alt="проверка работы серверов" src="https://github.com/user-attachments/assets/ca8cbe0f-de91-4622-96bb-e90a7f15c727" />

ps aux | grep "python3 server"

