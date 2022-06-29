**ALL**

```
enable
configure terminal
username SSHadmin password $cisco123!
ip domain-name final-dz.com
crypto key generate rsa general-keys modulus 1024
ip ssh version 2
line vty 0 4
transport input ssh
login local
exit
```
