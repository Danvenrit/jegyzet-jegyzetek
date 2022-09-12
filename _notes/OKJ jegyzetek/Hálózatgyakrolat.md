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

<img src="assets/alinterfesz_cucc.png">
![[alinterfesz_cucc.png]]

### Tétlenség beállítása, és logik block beállítása
- minden porton be kell állitan

- line console 0
- exec-timeout 2     (percben van)
- exit
- line vty 0 15
- exec-timeout 2
- exit
- login block-for 360 attempts 4 within 120   (ha 120 secen belül 4 szer rontja el 360 sec re blockolja)

### jelszavak beállítása
- line console 0
- pass   jelszó
- login
- exit
- line vty 0 15
- pass   jelszó
- login
- exit
- ser pass  (jelszó titkosítás)


### config elmentése vram-ba
- cop r st

### ftp server beállítása
- server
- services 
- ftp
- átnevezed az alap ciscot, jelszót adsz, add
- majd save

### routeren ftp user kreálása passworddal
- config mode
- ip ftp us Aladar
- ip ftp passw jelszó
- end
- cop r st

### tftp szerverre startup config mentése
- R3# mode
- cop st tftp 
- kéri a cél ip címet, általában a szerver gép
- utána kéri a fálj nevet, megadod, egyébként default nevet adni neki
- **ftp szerverre ugyan ez csak "cop st ftp" helyette**

### DNS szerver beállítása
- szerver gép
- services fül
- dns fül
- adsz neki nevet, ip cimet (pl c20.hu meg 192.158.0.70)
- addolod
- saveled
- onolod

### port description (port név)
- mindig a port nevét ird rá
- pl: se0/0/0- portnál
- int se0/0/0 
- des SE_000

### globális config szinten időzóna beállítása
- clo ti CEST 0   (clock timezone "a zóna")
-  mutatni úgy lehet az időt hogy
- R1# modban
- sh clo

### Óra beállítása
- R1# módban
- clock set 9:19:00 8 sep 2022

### switch alapkonfiguráció
- Switch# configure terminal
- Switch(config)# hostname HQSw1
- 
- **Configure the encrypted privileged EXEC password to 'class'.**
- HQSw1(config)# enable secret class
- 
- **Set all line passwords to 'cisco' and require a login, starting with the console. Set vty lines 0 through 15.**
- HQSw1(config)# line console 0
- HQSw1(config-line)# password cisco
- HQSw1(config-line)# login
- HQSw1(config-line)# line vty 0 15
- HQSw1(config-line)# password cisco
- HQSw1(config-line)# login
- **Exit to global configuration mode. Enter the command to encrypt the plain text passwords.**
- HQSw1(config-line)# exit
- HQSw1(config)# service password-encryption
- 
- **Configure VLAN 1 with the IP address 192.168.10.2/24 and activate the interface.**
- HQSw1(config)# interface vlan 1
- HQSw1(config-if)# ip address 192.168.10.2 255.255.255.0
- HQSw1(config-if)# no shutdown
- %LINK-5-CHANGED: Interface Vlan1, changed state to up
- 
- **Return directly to privileged EXEC mode and display the current configuration.**
- HQSw1(config-if)# end
- HQSw1# show running-config
- Building configuration...  
- Current configuration : 1178 bytes  
- !  
- version 12.2  
- no service timestamps log datetime msec  
- no service timestamps debug datetime msec  
- service password-encryption  
- !  
- hostname HQSw1  
- !  
- enable secret 5 $1$mERr$9cTjUIEqNGurQiFU.ZeCi1  
- !  
- !  
- < output omitted >  
- !  
- !  
- interface Vlan1  
- ip address 192.168.10.2 255.255.255.0  
- !  
- !  
- line con 0  
- password 7 0822455D0A16  
- login  
- !  
- line vty 0 4  
- password 7 0822455D0A16  
- login  
- line vty 5 15  
- password 7 0822455D0A16  
- login  
- !  
- !  
- end  
- HQSw1#




