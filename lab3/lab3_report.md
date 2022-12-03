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

Поднять Netbox на дополнительной VM.  
![image](https://user-images.githubusercontent.com/61542577/205424959-0e933652-2ffe-446c-add2-8a075f44e42f.png)

Используя браузер, подключить к Netbox по HTTPS.  
![image](https://user-images.githubusercontent.com/61542577/205425000-13c53e65-3a9c-4292-bf2f-360fcd5de1a3.png)

### 2. Заполнить информацию о CHR в Netbox
Заполнена информация о первом CHR.  
![image](https://user-images.githubusercontent.com/61542577/205425444-c3668a6c-cdc2-4406-9037-77862e37ca32.png)  
![image](https://user-images.githubusercontent.com/61542577/205425453-db266463-da2d-44cb-ab04-fc0dadbb5261.png)

Заполнена информация о втором CHR.  
![image](https://user-images.githubusercontent.com/61542577/205425470-bfc4bec1-a2d6-4330-bd2b-98171f094e06.png)  
![image](https://user-images.githubusercontent.com/61542577/205425482-b7b3ba67-040f-40eb-9e4f-effdab80a2b2.png)

### 3. Сохранить данные с Netbox в отдельный файл, используя Ansible

 


