**ALL**

```
enable
configure terminal
vlan 90
name MGMT
vlan 40
name IT_DEP
vlan 10 
name SERVER
vlan 50 
name EMPLOYEE
vlan 800
name PARKING_LOT
vlan 200
name TRUNK
```




**CORE-S1**

```
enable
configure terminal
spanning-tree vlan 10,40,50,90,200 root primary
int r fa0/1-2
channel-group 1 mode active
int port-channel 1
switchport mode trunk
switchport trunk allowed vlan 10,40,50,90,200
interface range f0/10-12
switchport mode trunk 
switchport trunk native vlan 200
switchport trunk allowed vlan 10,40,50,90,200
exit
int range f0/3-4
switchport mode access
switchport access vlan 10
exit
interface range fa0/5-9, fa0/13-24,g0/1-2
switchport mode access
switchport access vlan 800
exit
```

**CORE-S2**

```
enable
configure terminal
spanning-tree vlan 10,40,50,90,200 root secondary
channel-group 1 mode on
switchport mode trunk
switchport trunk allowed vlan 10,40,50,90,200
interface range f0/20-22, g0/1
switchport mode trunk 
switchport trunk native vlan 200
switchport trunk allowed vlan 10,40,50,90,200
exit
interface range fa0/3-19, fa0/23-24,g0/2
switchport mode access
switchport access vlan 800
exit
```

**CL-S1**

```
enable
configure terminal
interface range f0/10, f0/20
switchport mode trunk 
switchport trunk native vlan 200
switchport trunk allowed vlan 10,40,50,90,200
exit
int range f0/1-3
switchport mode access
switchport access vlan 40
exit
interface range fa0/4-9,  fa0/11-19, fa0/21-24,g0/1-2
switchport mode access
switchport access vlan 800
exit
```

**CL-S2**

```
enable
configure terminal
interface range f0/11, f0/21
switchport mode trunk 
switchport trunk native vlan 200
switchport trunk allowed vlan 10,40,50,90,200
exit
int range f0/1-3
switchport mode access
switchport access vlan 50
exit
interface range fa0/4-10,  fa0/12-20, fa0/22-24,g0/1-2
switchport mode access
switchport access vlan 800
exit
```

**CL-S3**

```
enable
configure terminal
enable
configure terminal
interface range f0/12, f0/22
switchport mode trunk 
switchport trunk native vlan 200
switchport trunk allowed vlan 10,40,50,90,200
exit
interface range fa0/4-11,  fa0/13-21, fa0/23-24,g0/1-2
switchport mode access
switchport access vlan 800
exit
```
