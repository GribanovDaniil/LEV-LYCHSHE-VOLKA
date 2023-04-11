# Ansible script for balnce servers web1 and web2

### В Inventory хранятся конфигурации (web_servers, rrobin)

### VagrantFile нужен, чтобы быстро поднять виртуалки.

### nginx.yml - это playbook для установки ПО (nginx) на сервера. Внутри него (плейбука) 3 роли: balancer, customer, selyavi. 

balancer - собственно сам балансировщик (настраивает балансировщик в round robin);

customer - сервера web1 или web2;

selyavi - отключает selinux и перезагружает сервер.

## Как запустить playbook?

### 1) Для начала следует закинуть в  inventory ip хостов с их именами.
### 2) После чего, для удобства просмотра и чтобы заметить изменения веб-страничек нужно в roles/templates/ поменять код шаблона html'a в файлике index.html.j2
### 3) Далее запускаем сам playbook (nginx.yml)
ansible-playbook nginx.yml -  исполняет все tasks файлы всех ролей, которые у нас прописаны.
### 4) В браузере в строке вписываем ipшник balacner'а ставим ":" и после пишем порт 8080.
## Вывод:

![image_2023-04-10_21-19-42](https://user-images.githubusercontent.com/113581434/231002014-aaed9abc-4269-436d-9729-64494916ef2a.png)
![IMG_2618](https://user-images.githubusercontent.com/113581434/231001853-c3f8c4fd-69c5-4cfb-a495-3529e155a9ca.PNG)
![IMG_2619](https://user-images.githubusercontent.com/113581434/231001965-e70c6fab-ed8b-41fd-b7b1-3747558ff0e9.PNG)
# Лев не оборачивается, когда лает маленькая собака
