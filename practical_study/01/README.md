## Базовая настройка коммутатора 

### Часть 1. Проверка конфигурации коммутатора по умолчанию
### Часть 2. Создание сети и настройка основных параметров устройства
### Часть 3. Проверка сетевых подключений

### Решение

1. [Топология](./otus-practical-study-01.png)
2. Настройка Switch
- базовые парамметры

```
enable
configure terminal
no ip domain-lookup
hostname S1
service password
service password-encryption 
enable secret class
banner motd #Unauthorized access is strictly prohibited. #
exit
```

- настройка svi

```
configure terminal
interface vlan 1
ip address 192.168.1.2 255.255.255.0
no shutdown
exit
```
- ограничение доступа до порта консоли
```
configure terminal
line con 0
logging synchronous 
exit
```
- настройка vty
```
configure terminal
line vty 0 4
password class
login
exit
```
- [настройка ip address на ПК](./otus-dz-1-pc-config.png)


3. Проверка сетевых подключений
- [Ping](./otus-dz-1-ping-test.png)
- [Удаленное подключение](./otus-dz-1-remote-connection.png)

4. [Конфигурационный файл, после выполенния заданий](./config)
