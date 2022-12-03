University: [ITMO University](https://itmo.ru/ru/)  
Faculty: [FICT](https://fict.itmo.ru)  
Course: [Network programming](https://github.com/itmo-ict-faculty/network-programming)  
Year: 2022/2023  
Group: K34212  
Author: Ekaterina Telegina  
Lab: Lab2  
Date created:  
Date finished: 
# 
## ЦЕЛЬ РАБОТЫ
С помощью Ansible настроить несколько сетевых устройств и собрать информацию о них. Правильно собрать файл Inventory.
### ХОД РАБОТЫ
### 1. Установка Wireguard туннели
**Конфигурация сервера Wireguard на виртуальной машине в Яндексе**  
Сгенерирована и сохранена пара открытого и закрытого ключей для сервера.  
![image](https://user-images.githubusercontent.com/61542577/205404945-5ba13f11-3f4e-447e-869b-604b0443e0b4.png)  

Редактирован файл конфигурации сервера Wireguard /etc/wireguard/wg0.conf  
![image](https://user-images.githubusercontent.com/61542577/205414722-545e332d-ee39-4c32-bb87-f3f83a2d2d48.png)  
Данная конфигурация дает серверу адрес 192.168.0.1 и позволяет серверу послушать на порт 51820 для входящих пакетов.

Запущен интерфейс Wireguard.  
![image](https://user-images.githubusercontent.com/61542577/205410343-a9d492a6-ffe2-4432-832a-02651d15840d.png)

**Конфигурация клиента Wireguard на 2-х CHR**  
Добавлен интерфейс Wireguard и назначен ему IP адрес 192.168.0.2  
![image](https://user-images.githubusercontent.com/61542577/205414850-56c33f66-7f70-4d8a-8753-87e3af316638.png)  
![image](https://user-images.githubusercontent.com/61542577/205414875-c21d059c-edda-48fc-9947-a42bfbbceb2a.png)  

На CHR добавлен Wireguard пир, указав необходимые параметры сервера.  
![image](https://user-images.githubusercontent.com/61542577/205414943-240f95ed-20d6-42b6-8d85-46342dd6b395.png)

На сервере добавлен Wireguard пир, указав необходимые параметры клиента.  
![image](https://user-images.githubusercontent.com/61542577/205415794-1ba20490-1a7f-452f-8311-b130d57f26e9.png)

Повторить процесс для второго CHR, которому назначен IP адрес 192.168.0.3

### 2. Настройка CHR при помощи Ansible
Проверка наличия Ansible.  
![image](https://user-images.githubusercontent.com/61542577/205417777-41319cb5-af6d-44a4-a1de-5a53ba52c15c.png)

Редактирован файл hosts, в котором указаны адресы двух CHR.  
![image](https://user-images.githubusercontent.com/61542577/205421363-6cc371ae-1a04-4dae-8751-c99f64de158e.png)

Создан плейбук, который добавит нового пользователей, настроит NTP сервер и настроит OSPF на двух CHR.  
![image](https://user-images.githubusercontent.com/61542577/205421388-1afa8714-6228-482c-935a-82ce46f87b28.png)

Запущен плейбук.  
![image](https://user-images.githubusercontent.com/61542577/205421414-e0516078-979b-426a-b035-3db1ef948ba0.png)

Создан плейбук, который собирает данные по OSPF топологии и полный конфиг двух CHR. Конфиг устройства сохранен в отдельные файлы  
![image](https://user-images.githubusercontent.com/61542577/205422380-e7bc94db-ea39-449f-9230-18e8f865a705.png)

Запущен сценарий.  
![image](https://user-images.githubusercontent.com/61542577/205422440-f0055961-1456-45a3-9ce9-c7fbd6847610.png)

### 3. Результаты
В результате получаем 2 файла с конфигурациями устройств и связь по следующей схеме.  













