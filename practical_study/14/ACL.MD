```
en 
conf t
ip access-list extended vlan90
remark SSH_SW
permit ip 192.168.40.0 0.0.0.255 192.168.90.0 0.0.0.255
remark PING
permit icmp any any
deny ip any any
exit
int g0/0/1.90
ip access-group vlan90 out
exit
```


ip access-list extended empolyee-in
remark DENY-SSH
deny tcp any any eq 22
remark ALLOW OTHER
permit ip any any
int g0/0/1.50
ip access-group empolyee-out in