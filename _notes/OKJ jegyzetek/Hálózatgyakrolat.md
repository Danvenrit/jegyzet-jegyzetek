#### Alinterfész kialakitása
-  routeren

- int g0/0.10 (ha a gateway g0/0)
- encapsulation dot1q 10 (a 10 a 0.10)
- ip-t adsz a portnak maskal

#### Vlan létrehozása
- switchen 

- vlan 10 
- name tizes
- ex
- fa 0/1 (az alinterfész potjta)
- switchport mode access //elérhetővé teszi
- switchport access vlan 10 //felveszed a vlan 10 be
- int g0/1 (a default gateway cime)
- switchport mode trunk 

- ezután már lehet dhcp 
<img src="asstets/alinterfesz_cucc-png">
![[alinterfesz_cucc.png]]