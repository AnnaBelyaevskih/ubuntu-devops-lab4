# Лабораторная работа №4: Автоматизация развертывания с помощью Ansible

## Ход выполнения работы

### 1. Создание пользователя runner
Создание пользователя `runner` на `managed-node` и добавление его в группу `sudo`.

![scr1](./screenshots/scr1.png)

### 2. Проверка доступности по SSH
Успешное подключение по SSH к узлу `runner@10.0.2.16`.

![scr2](./screenshots/scr2.png)

### 3. Проверка связности через Ansible
Выполнение `ansible -i inventory webservers -m ping` (получен ответ `pong`).

![scr3](./screenshots/scr3.png)

### 4. Настройка NOPASSWD в sudoers
Добавление строки `runner ALL=(ALL) NOPASSWD:ALL` в `/etc/sudoers`.

![scr4](./screenshots/scr4.png)

### 5. Создание структуры проекта
Создание директории `lab-ansible` и файлов `playbook.yml` и `inventory.ini`.

![scr5](./screenshots/scr5.png)

### 6. Настройка инвентарного файла
Заполнение `inventory.ini` с группой `[webservers]` и IP-адресом `10.0.2.16`.

![scr6](./screenshots/scr6.png)

### 7. Написание плейбука для Nginx
Создание `playbook.yml` с задачей установки Nginx через модуль `apt`.

![scr7](./screenshots/scr7.png)

### 8. Проверка плейбука (--check)
Запуск плейбука в режиме тестирования с флагом `--check`.

![scr8](./screenshots/scr8.png)

### 9. Запуск плейбука
Выполнение плейбука и установка Nginx на управляемый узел.

![scr9](./screenshots/scr9.png)

### 10. Создание HTML-страницы
Создание файла `index.html` с текстом `Hello from Ansible playbook!`.

![scr10](./screenshots/scr10.png)

### 11. Обновление плейбука
Добавление в `playbook.yml` задачи копирования `index.html` через модуль `copy`.

![scr11](./screenshots/scr11.png)

### 12. Финальный запуск плейбука
Повторный запуск плейбука и успешная передача файла HTML (`changed=1`).

![scr12](./screenshots/scr12.png)

### 13. Проверка работы через curl
Проверка ответа веб-сервера командой `curl http://10.0.2.16`.

![scr13](./screenshots/scr13.png)

### 14. Проверка в браузере
Проверка отображения страницы в браузере по адресу `localhost:8081`.

![scr14](./screenshots/scr14.png)
