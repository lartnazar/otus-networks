**ISP-R1**

```
enable
configure terminal
interface g0/0/1
no shutdown 
exit
interface g0/0/1.10
encapsulation dot1Q 10
ip address 192.168.10.1 255.255.255.0
exit
interface g0/0/1.40
encapsulation dot1Q 40
ip address 192.168.40.1 255.255.255.0
exit
interface g0/0/1.50
encapsulation dot1Q 50
ip address 192.168.50.1 255.255.255.0
exit
interface g0/0/1.90
encapsulation dot1Q 90
ip address 192.168.90.254 255.255.255.0
exit
interface g0/0/1.200
encapsulation dot1Q 200 native
exit
```