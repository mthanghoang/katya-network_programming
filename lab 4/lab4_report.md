University: [ITMO University](https://itmo.ru/ru/)  
Faculty: [FICT](https://fict.itmo.ru)  
Course: [Network programming](https://github.com/itmo-ict-faculty/network-programming)  
Year: 2022/2023  
Group: K34212  
Author: Ekaterina Telegina  
Lab: Lab 4  
Date created:  
Date finished: 
# 
## ЦЕЛЬ РАБОТЫ
Изучить синтаксис языка программирования P4 и выполнить 2 задания обучающих задания от Open network foundation для ознакомления на практике с P4.
## ХОД РАБОТЫ
## 1. Basic Forwarding
Перед выполнением задания с помощью Vagrant была установлена виртуальная машина, на которой имеются все необходимые программы. Подключить к машине под учетной записи p4 и заходить в папку с упраженениями.  
![image](https://user-images.githubusercontent.com/61542577/205453181-bfd5ec5f-70fb-461a-b76c-beddd0d9a71c.png)

Цель этого упражнения — написать программу P4, реализующую базовую переадресацию для ipv4. Идея задачи в том, что коммутатор должен выполнять следующие действия для каждого пакета: обновлять MAC-адреса источника и получателя, уменьшать время жизни (TTL) в заголовке IP и пересылать пакет на соответствующий порт.

Схема связи представлена ниже.  
![image](https://user-images.githubusercontent.com/61542577/205452916-09af2b37-334b-4f7b-8df0-f56a77c239fa.png)

### Запустить имеющий
