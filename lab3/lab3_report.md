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
С помощью Ansible и Netbox собрать всю возможную информацию об устройствах и сохранить их в отдельном файле.
## ХОД РАБОТЫ
### 1. Поднять Netbox на дополнительной VM
Создана новая VM, которая соединена с VM на Яндексе через Wireguard туннель.

Поднять Netbox на новой VM.  
![image](https://user-images.githubusercontent.com/61542577/205424959-0e933652-2ffe-446c-add2-8a075f44e42f.png)  
![image](https://user-images.githubusercontent.com/61542577/205443062-64a17558-43cc-4d32-b5a6-601604be95a7.png)


Используя браузер, подключить к Netbox по порту 8000.  
![image](https://user-images.githubusercontent.com/61542577/205443077-fab0ccde-545e-44eb-8401-4ff4dd6ec0a6.png)

### 2. Заполнить информацию о CHR в Netbox
Заполнена информация о первом CHR.  
![image](https://user-images.githubusercontent.com/61542577/205425444-c3668a6c-cdc2-4406-9037-77862e37ca32.png)  
![image](https://user-images.githubusercontent.com/61542577/205425453-db266463-da2d-44cb-ab04-fc0dadbb5261.png)

Заполнена информация о втором CHR.  
![image](https://user-images.githubusercontent.com/61542577/205425470-bfc4bec1-a2d6-4330-bd2b-98171f094e06.png)  
![image](https://user-images.githubusercontent.com/61542577/205425482-b7b3ba67-040f-40eb-9e4f-effdab80a2b2.png)

### 3. Сохранить данные с Netbox в отдельный файл, используя Ansible
Редактирован файл hosts, добавлен адрес по которому подключить к Netbox  
![image](https://user-images.githubusercontent.com/61542577/205442012-3ce5c310-0343-43bd-94db-106080c50fae.png)

Создан API токен для обращения к Netbox плейбуком.  
![image](https://user-images.githubusercontent.com/61542577/205442842-d1e1e753-ca51-4607-83f3-3e088dfc3b6e.png)

Плейбук, который собирает все данные из Netbox. Необходимо установить pynetbox для использования плагин nb_lookup.  
![image](https://user-images.githubusercontent.com/61542577/205444727-7c23cb21-03f0-4306-920b-39fb92a0359c.png)

Запущен плейбук.  
![image](https://user-images.githubusercontent.com/61542577/205444874-89ffdd86-b421-45ab-a75d-1862e6cb2a5e.png)

### 4. На основе данных из Netbox настроить 2 CHR
Плейбук, который на основе собранных данных из Netbox изменит имя устроства и добавит IP адрес на 2-х CHR.  
![image](https://user-images.githubusercontent.com/61542577/205447154-e71ef145-4f74-4c43-8edb-b4fb987cdd3a.png)

Запущен плейбук.  
![image](https://user-images.githubusercontent.com/61542577/205447198-46b54f72-658b-4a88-87e3-977fc9a98cb0.png)  
![image](https://user-images.githubusercontent.com/61542577/205447219-465dc3f6-d683-4e78-86bd-fe8e9c4d8faf.png)

### 5. Написать сценарий, позволяющий собрать серийный номер устройства и вносящий серийный номер в Netbox
Плейбук позволяющий собрать серийный номер устройства и вносящий серийный номер в Netbox.  
![image](https://user-images.githubusercontent.com/61542577/205449233-a787fa94-ef16-4bf6-ad9f-ad9d6a71f31e.png)

Запущен плейбук.  
![image](https://user-images.githubusercontent.com/61542577/205449369-0711421d-c6a5-4617-bd6e-6847e166a55d.png)

Серийный номер в Netbox добавлен.  
![image](https://user-images.githubusercontent.com/61542577/205449588-385266e1-cad9-4d0a-be03-9677680eae45.png)  
![image](https://user-images.githubusercontent.com/61542577/205449597-98c70af2-7bbb-417c-b614-b0ad86ba4b96.png)

## РЕЗУЛЬТАТЫ
Получаем файл netbox_data.json с данными, собранными с Netbox.  
Получаем связь по следующей схеме.  
![image](https://user-images.githubusercontent.com/61542577/205472341-9683aefe-c27c-4f70-afda-3655b78a1705.png)



