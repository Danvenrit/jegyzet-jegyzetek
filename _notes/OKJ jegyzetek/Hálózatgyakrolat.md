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


