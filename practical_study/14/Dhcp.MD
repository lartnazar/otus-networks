**ISP-R1**

```
enable
configure terminal
ip dhcp excluded-address 192.168.40.1 192.168.40.5
ip dhcp pool IT_pool
network 192.168.40.0 255.255.255.0
domain-name final-dz.com
default-router 192.168.40.1
exit
ip dhcp excluded-address 192.168.50.1 192.168.50.5
ip dhcp pool Employee_pool
network 192.168.50.0 255.255.255.0
domain-name final-dz.com
default-router 192.168.50.1
exit
do copy running-config startup-config 
```