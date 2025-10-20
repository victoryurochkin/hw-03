# Домашнее задание к занятию «Система мониторинга Zabbix. Часть 2» - `Юрочкин В.А.`

### Задание 1
Создайте свой шаблон, в котором будут элементы данных, мониторящие загрузку CPU и RAM хоста.


`1. Создаём шаблоны`

<img width="1919" height="990" alt="Screenshot_1" src="https://github.com/user-attachments/assets/4b12474a-6b92-4b4b-863f-bbfca63cc616" />

`Заполняем шаблон`

<img width="1919" height="994" alt="Screenshot_2" src="https://github.com/user-attachments/assets/c005ccc2-b602-4d79-b663-13713637f373" />

`находим наш созданный шаблон для добавления “итемов”, “проваливаемся” в него`

<img width="1919" height="999" alt="Screenshot_1" src="https://github.com/user-attachments/assets/08680eaf-41c2-4ae3-9b1d-2a97f34a7a97" />

`добавляем новый “итем” для мониторинга CPU`

<img width="1919" height="997" alt="Screenshot_3" src="https://github.com/user-attachments/assets/f91d2444-9a5f-4761-9d3a-bba46081a5d9" />

`заполняем и добавляем`

<img width="1919" height="992" alt="Screenshot_4" src="https://github.com/user-attachments/assets/19318a95-1c54-488c-a285-ffb41947d295" />

`для RAM - заполняем и добавляем`

<img width="1919" height="994" alt="Screenshot_5" src="https://github.com/user-attachments/assets/e3342e88-7234-4786-946b-6f3f4c54cbd5" />

---

### Задание 2 - Добавьте в Zabbix два хоста и задайте им имена <фамилия и инициалы-1> и <фамилия и инициалы-2>. Например: ivanovii-1 и ivanovii-2.


`ППроцесс выполнения
Выполняя ДЗ сверяйтесь с процессом отражённым в записи лекции.
Установите Zabbix Agent на 2 виртмашины, одной из них может быть ваш Zabbix Server
Добавьте Zabbix Server в список разрешенных серверов ваших Zabbix Agentов
Добавьте Zabbix Agentов в раздел Configuration > Hosts вашего Zabbix Servera
Прикрепите за каждым хостом шаблон Linux by Zabbix Agent
Проверьте что в разделе Latest Data начали появляться данные с добавленных агентов`

`Решение:`

`Ранее я уже устанавливал агенты на свои ВМ, воспользуюсь ими для выполнения этого домашнего задания

скриншот демонстрирует всё необходимое по заданию 2`

<img width="1919" height="1001" alt="Screenshot_6" src="https://github.com/user-attachments/assets/c59fdcaa-93dc-4f29-80fc-7cd7b6b1f75c" />

---

### Задание 3 - Привяжите созданный шаблон к двум хостам. Также привяжите к обоим хостам шаблон Linux by Zabbix Agent.

`Процесс выполнения
Выполняя ДЗ сверяйтесь с процессом отражённым в записи лекции.
Зайдите в настройки каждого хоста и в разделе Templates прикрепите к этому хосту ваш шаблон
Так же к каждому хосту привяжите шаблон Linux by Zabbix Agent
Проверьте что в раздел Latest Data начали поступать необходимые данные из вашего шаблона`

`Решение:`

`Добавим нашим узам ранее созданный шаблон`

<img width="1919" height="998" alt="Screenshot_3" src="https://github.com/user-attachments/assets/ab2f0320-72af-4bb5-9505-86efba11b047" />

<img width="1919" height="1001" alt="Screenshot_4" src="https://github.com/user-attachments/assets/947430c6-dfee-4711-a589-eacd80a1e0bc" />

<img width="1919" height="999" alt="Screenshot_7" src="https://github.com/user-attachments/assets/4d9fae55-03ed-4e84-b6c6-596b410905f2" />

`смотрим отдаваемые узлами метрики`

<img width="1919" height="995" alt="Screenshot_9" src="https://github.com/user-attachments/assets/91e2e5a0-0feb-48bf-abc7-2565c9fbf81f" />

<img width="1919" height="994" alt="Screenshot_10" src="https://github.com/user-attachments/assets/94e814b3-7a12-48af-816b-0c772dfcb60e" />

<img width="1919" height="990" alt="Screenshot_11" src="https://github.com/user-attachments/assets/ca3444b3-3d2b-4568-9dc3-738c70eff66e" />

<img width="1919" height="991" alt="Screenshot_12" src="https://github.com/user-attachments/assets/bf9d85a0-aefe-4e6f-8d50-c765e957cbf8" />

---

### Задание 4 - Создайте свой кастомный дашборд.

`Процесс выполнения
Выполняя ДЗ сверяйтесь с процессом отражённым в записи лекции.
В разделе Dashboards создайте новый дашборд
Разместите на нём несколько графиков на ваше усмотрение.`

`Решение:`

`Создаю дашборд`

<img width="1919" height="994" alt="Screenshot_13" src="https://github.com/user-attachments/assets/04754652-cfa4-4a2a-8caf-b1826d30026f" />

`Результат на скриншоте`

<img width="1919" height="998" alt="Screenshot_5" src="https://github.com/user-attachments/assets/a439f930-7026-4bf3-9920-ccaf65e75680" />

<img width="1919" height="994" alt="Screenshot_6" src="https://github.com/user-attachments/assets/3c1ff469-bd2d-4920-95f7-57053abf75aa" />










