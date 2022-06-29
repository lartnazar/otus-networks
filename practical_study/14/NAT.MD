**ISP-R1**

```
en 
conf t
ip nat inside source static tcp 192.168.10.10 80 209.165.200.229 80
ip nat inside source static tcp 192.168.10.10 443 209.165.200.229 443
int g0/0/1.10 
ip nat inside 
exit
int g0/0/0
ip address 209.165.200.230 255.255.255.248
ip nat outside
no shutdown
exit
ip route 0.0.0.0 0.0.0.0 209.165.200.225

```

**TEST-R**

```


enable
configure terminal
ip nat inside source static 192.168.200.2 209.165.200.228
interface gigabitEthernet 0/0/0
ip address 209.165.200.225 255.255.255.248
no sh
exit
ip route 0.0.0.0 0.0.0.0 209.165.200.230
int g0/0/1
ip address 192.168.200.1 255.255.255.0
no sh
```