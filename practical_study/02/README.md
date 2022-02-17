### Просмотр таблицы MAC-адресов коммутатора 

## Настройка сети

1. [Топология](./otus-dz-2-topology.png)
2. Настройка коммутатора
- S1
```
enable
configure terminal
hostname S1
service password-encryption 
enable secret class
interface vlan 1
ip address 192.168.1.11 255.255.255.0
no shutdown
exit
line con 0
password cisco
login
exit
line vty 0 4
password cisco
login
exit
```
[Config_file](./s1_config)
- S2

```
enable
configure terminal
hostname S2
service password-encryption 
enable secret class
interface vlan 1
ip address 192.168.1.12 255.255.255.0
no shutdown
exit
line con 0
password cisco
login
exit
line vty 0 4
password cisco
login
exit
```
[Config_file](./s2_config)

2. Изучение таблицы МАС-адресов коммутатора
- PC-A
mac:  0030.F2EB.511A

- PC-B
mac: 0090.0C14.646E

- S1
mac: 0001.c710.8e01

- S2 
mac: 0002.1731.ca01

[Таблица mac адерсов](./otus-dz-2-mac-address-table-S2.png)