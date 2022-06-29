**CORE-S1**

```
enable
configure terminal
hostname CORE-S1
no ip domain-lookup
enable secret class
line con 0
password cisco
login
exit
line vty 0 4
password cisco
login
exit
service password-encryption 
banner motd |Authorized Users Only|
interface vlan 90
ip address 192.168.90.1 255.255.255.0
exit
interface range fa0/5-9, fa0/13-24,g0/1-2
shutdown
exit
ip default-gateway 192.168.90.254
exit
clock set 22:00:00 26 jun 2022
copy run st

```

**CORE-S2**

```
enable
configure terminal
hostname CORE-S2
no ip domain-lookup
enable secret class
line con 0
password cisco
login
exit
line vty 0 4
password cisco
login
exit
service password-encryption 
banner motd |Authorized Users Only|
interface vlan 90
ip address 192.168.90.2 255.255.255.0
exit
interface range fa0/3-19, fa0/23-24,g0/2
shutdown
exit
ip default-gateway 192.168.90.254
exit
clock set 22:00:00 26 jun 2022
copy run st

```


**CL-S1**

```
enable
configure terminal
hostname CL-S1
no ip domain-lookup
enable secret class
line con 0
password cisco
login
exit
line vty 0 4
password cisco
login
exit
service password-encryption 
banner motd |Authorized Users Only|
interface vlan 90
ip address 192.168.90.21 255.255.255.0
exit
interface range fa0/4-9,  fa0/11-19, fa0/21-24,g0/1-2
shutdown
exit
ip default-gateway 192.168.90.254
exit
clock set 22:00:00 26 jun 2022
copy run st

```

**CL-S2**

```
enable
configure terminal
hostname CL-S2
no ip domain-lookup
enable secret class
line con 0
password cisco
login
exit
line vty 0 4
password cisco
login
exit
service password-encryption 
banner motd |Authorized Users Only|
interface vlan 90
ip address 192.168.90.22 255.255.255.0
exit
interface range fa0/4-10,  fa0/12-20, fa0/22-24,g0/1-2
shutdown
exit
ip default-gateway 192.168.90.254
exit
clock set 22:00:00 26 jun 2022
copy run st
```

**CL-S3**

```
enable
configure terminal
hostname CL-S3
no ip domain-lookup
enable secret class
line con 0
password cisco
login
exit
line vty 0 4
password cisco
login
exit
service password-encryption 
banner motd |Authorized Users Only|
interface vlan 90
ip address 192.168.90.23 255.255.255.0
exit
interface range fa0/4-11,  fa0/13-21, fa0/23-24,g0/1-2
shutdown
exit
ip default-gateway 192.168.90.254
exit
clock set 22:00:00 26 jun 2022
copy run st
```


**ISP-R1**

```
enable
configure terminal
hostname ISP-R1
no ip domain-lookup
enable secret class
line con 0
password cisco
login
exit
line vty 0 4
password cisco
login
exit
service password-encryption 
banner login |Authorized Users Only|
exit
copy running-config startup-config 
```