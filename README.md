# Домашнее задание к занятию "`Git`" - `Клименко Олег`


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


1. `Аккаунт зарегистрирован, репозиторий создан` `тут мы уже видим что в репозитории что-то имеется,дело в том что работу я уже сделал,и разбирался как правильно вставлять скриншоты хыхыхы`
![](https://cdn.discordapp.com/attachments/1217104862043570196/1224625079061712906/image.png?ex=661e2bfb&is=660bb6fb&hm=55778dc683c0b31ba2f8bc467b2d831e0cce4e38f722a02575693994ce0a575a&)
2. `Склонирую репозиторий используя SSH ключ`
*  `Добавляю ключ в github, и выполняю **git clone**`
![](https://cdn.discordapp.com/attachments/1217104862043570196/1224363492149301379/image.png?ex=661d385c&is=660ac35c&hm=7ea311358be49250ba2c04c81f55b0e4c28c90018a6a36655dc31620c05b6f51&)
3. `Перехожу в каталог с клоном репозитория`
![](https://cdn.discordapp.com/attachments/1217104862043570196/1224363640476401837/image.png?ex=661d387f&is=660ac37f&hm=56410752b5ba8438bdff9828ad87af85f9d545cf5f295dd137889ba58ae4eb64&)
4. `произвожу первоначальную настройку **Git**`
![](https://cdn.discordapp.com/attachments/1217104862043570196/1224363943020068935/image.png?ex=661d38c7&is=660ac3c7&hm=c70f85bc1e2e2c8e7c1bfdae3d722d9f95c346ced19c98833b4920e41a255c21&)
5. `Выполняю команду **git status** и запоминаю результат`
![](https://cdn.discordapp.com/attachments/1217104862043570196/1224364070782767244/image.png?ex=661d38e6&is=660ac3e6&hm=6d3439951af45b63785e469d04ccda1a8a156415ce9b47686505e3a55c0f5665&)
6. `Редактирую файл **README.md** при помощи nano, файл в состоянии **Modified**.`
![](https://cdn.discordapp.com/attachments/1217104862043570196/1224364329298690170/image.png?ex=661d3923&is=660ac423&hm=e7a03b19235e87e5e389c0e9c374500b3f8cb21f3d8fb38c19d401346470c103&)
7. `Ещё раз выполняю **git status** и продолжу проверять вывод этой команды после каждого следующего шага.`      
![](https://cdn.discordapp.com/attachments/1217104862043570196/1224364429978636298/image.png?ex=661d393b&is=660ac43b&hm=c7bcad5f992a6ce5da289688209549932350b9735c044a9f8c71f5de25529f25&)
8. `Смотрю изменения в файле README.md, выполняю команды git diff и git diff --staged.`
![](https://cdn.discordapp.com/attachments/1217104862043570196/1224364591006355577/image.png?ex=661d3962&is=660ac462&hm=c584485debe235906112c712e1f405b516c2745d62d5e09c141753018c20d7fb&)
9. `Перевожу файл в состояние **staged**, добавляю файл в коммит, командой **git add README.md**.`
![](https://cdn.discordapp.com/attachments/1217104862043570196/1224364777409871903/image.png?ex=661d398e&is=660ac48e&hm=00c007244f84efe4ed31936b0047b2f8b6d20a50757547646a78b1f19d8876b4&)
10. `Ещё раз выполню команды **git diff** и **git diff --staged**.`
![](https://cdn.discordapp.com/attachments/1217104862043570196/1224364948277170216/image.png?ex=661d39b7&is=660ac4b7&hm=065108255724e2e33100c89fcfe64e287d3fbcd61f9643d9ab6b27643e64032c&)   
11. `Сделаю коммит *git commit -m 'First commit'*.`
![](https://cdn.discordapp.com/attachments/1217104862043570196/1224365147032916119/image.png?ex=661d39e6&is=660ac4e6&hm=8a2cb490ce14d1666defacbfe0c576ed8a915c8e04d1d2a98664c645a6bb9b19&)
12. `Делаю **git push origin** .`
![](https://cdn.discordapp.com/attachments/1217104862043570196/1224365544644546571/image.png?ex=661d3a45&is=660ac545&hm=c203a45ef13ec3eca4e045fa79dc2ee4b743b1e4c3fe66f0bc19aa4b08bc96c7&)
---
![](https://cdn.discordapp.com/attachments/1217104862043570196/1224629685191970836/image.png?ex=661e3045&is=660bbb45&hm=d7e78418df13d61ddb728d6ec18932722d8f0bdc97e5f5f66298ae7698969a4e&)
---


---

### Задание 2


1. `Создаю файл .gitignore, проверяю его статус сразу после создания.`
   ![](https://cdn.discordapp.com/attachments/1217104862043570196/1224365796315238430/image.png?ex=661d3a81&is=660ac581&hm=a71c4759c00f33c3a19a78584949c7200892cc2ac726ada05294ec617827967a&)
2. `Добавляю файл .gitignore в коммит git add .gitignore`
   ![](https://cdn.discordapp.com/attachments/1217104862043570196/1224365973075792043/image.png?ex=661d3aab&is=660ac5ab&hm=0397a324b7279983073af3288c17f28784d2e8fea7ba3840ef4139f7cb417ef2&)
3. `Добавляю правила в файл .gitignore, чтобы игнорировать любые файлы .pyc, а также все файлы в директории cache.`
   ![](https://cdn.discordapp.com/attachments/1217104862043570196/1224366252550525061/image.png?ex=661d3aee&is=660ac5ee&hm=8f730c0ad141f603d9948a77fde68eb25d0c21d1b29810f3ced0b8251dabc4e9&)
4. `Делаю комит и пуш`
   ![](https://cdn.discordapp.com/attachments/1217104862043570196/1224366563474542743/image.png?ex=661d3b38&is=660ac638&hm=668d22c1eaeaad84750f1244bef943b6d77882a556d7a6df09a337de05d3305c&)
 

---

### Задание 3


1. `Создаю новую ветку dev и сразу переключаюсь на неё. git checkout -b dev`
2. `Создаю файл test.sh с произвольным содержимым.`
   ![](https://cdn.discordapp.com/attachments/1217104862043570196/1224366867133628476/image.png?ex=661d3b80&is=660ac680&hm=57da6995d56579703273e1afc1794b0a297e9c85ea2111cdd186b8443024676a&)
4. `Сделаю несколько коммитов и пушей, имитируя активную работу над файлом test.sh.`
   ![](https://cdn.discordapp.com/attachments/1217104862043570196/1224367600511881256/image.png?ex=661d3c2f&is=660ac72f&hm=a7a61b45e569726711dbcbb847af7df3433c56430ef0a63123f481548b6148dc&)
6. `Сделайте мердж этой ветки в основную. Сначала нужно переключиться на неё, а потом вызывать git merge.`
   ![](https://cdn.discordapp.com/attachments/1217104862043570196/1224368496629256274/image.png?ex=661d3d05&is=660ac805&hm=69463750c66cc4077aacd05982039bbe5306a2b702fed8efd869b5b174aaca66&)
8. `Сделайте коммит и пуш.`
   ![](https://cdn.discordapp.com/attachments/1217104862043570196/1224368980232376321/image.png?ex=661d3d78&is=660ac878&hm=fd46c4820688a20c093314ccad5583a5f5a0b318aa404e843a8c68d2ac1ad7f0&)

---
![](https://cdn.discordapp.com/attachments/1217104862043570196/1224632703924572170/image.png?ex=661e3315&is=660bbe15&hm=b3ef80769ce0a10d405ae713fda22e437e434661202505a4ce2650614a6e4e26&)
---
```
