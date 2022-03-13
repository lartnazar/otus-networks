
## Настройка IPv6-адресов на сетевых устройствах 
[Топология](./otus-dz-4-topology.png)

0.
#### Предварительная настройка коммутатора
- **S1**

```
enable
configure terminal
sdm prefer dual-ipv4-and-ipv6 default
end
reload
```
1.
### Настройка маршрутизатор и коммуникатора

- **R1**
```
enable
configure terminal
hostname R1
service password-encryption 
enable secret class
line con 0
password cisco
login
exit
line vty 0 4
password cisco
login
exit
```

- **S1**
```
enable
configure terminal
hostname S1
service password-encryption 
enable secret class
line con 0
password cisco
login
exit
line vty 0 4
password cisco
login
exit
```
2.
### Ручная настройка IPv6-адресов

 - **R1**
 
```
enable
configure terminal
interface gigabitEthernet 0/0/0
ipv6 address 2001:db8:acad:a::1/64
ipv6 address fe80::1 link-local
no shutdown
end
configure terminal
interface gigabitEthernet 0/0/1
ipv6 address 2001:db8:acad:1::1/64
address fe80::1 link-local 
no shutdown
```
[Router Interfeces](./otus-dz-4-router-interfaces.png)

- **PC-B**
[PC-interfaces-link-local](./otus-dz-4-pc-b-auto-ipv6.png)


- **R1**
```
enable
configure terminal 
ipv6 unicast-routing
```
[Router Interfaces](./otus-dz-4-router-interface-ipv6-routing-1.png)

- **PC-B**

[PC-B-SLAAC](./otus-dz-4-pc-b-slaac.png)

- **S1**
```
enable
configure terminal
interface vlan 1
ipv6 address 2001:db8:acad:1::3/64
ipv6 address fe80::2 link-local
end
```
[Switch-Vlan1](./otus-dz-4-s1-vlan1.png)

3.
## Проверка сквозного подключения
 - **PC-A**

 [ping-pc-a-gw](./otus-dz-4-ping-pc-a-gw.png)

 [tracert-pc-a-pc-b](./otus-dz-4-pc-a-tracert-pc-b.png)
 
 - **PC-B**

 [ping-pc-b-pc-a](./otus-dz-4-pc-b-ping-pc-a.png)

 [ping-pc-b-gw](./otus-dz-4-pc-b-ping-gw.png)