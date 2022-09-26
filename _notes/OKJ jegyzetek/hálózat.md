# 1. óra (2022.09.06)
- Fontos a dokumentálás, hasznos magadnak is, de rendszergazdaváltáskor nagy segítség 
- A hálózat megfelelő rendeltetése, több dologtól függ, pl: a készülékek állapotától.
- két véglet van, a nagyon modern tökéletesen működő, meg a már végsőket rugó régi rendszer
- fontos egy rendszer adatforgalmát csekkolni, ebből sok mindent meg lehet tudni
- sok mindennel lehet segiteni: dokumentáció, esetleges kábelek cetlizése is (mi hova megy)
- az is potenciálisan rosz, vagy jó, hogy egy régi rendszert felturbóz a nagyon fasza rendszergazda, csak ha utána megy egy kevésbé fasza, akkor fingja se lesz róla
- ha pl programokat ír egy rendszergazda stb, stb, nem egyben megcsinálod a dolgokat hanem egyszerre több dolgot, és pl 2 hét múlva tud csak megint hozzányúlni a kódhoz, ilyenkor jó ha normálisan commentelve van

### Konvergens hálózatok
- **konvergencia**: amikor bekapcsolódik egy rendszer akkor történnie kell dolgoknak (ha bekapcsol egy router nem fog instant működni)
	- **konvergált hálózat:** egy hálózat akkor konvergált ha minden be van állítva, konfigurálva, és már rendeltetésszerűen használható
	- hálózatoknál fontos, hogy a rendszergazda tudjon bonyolult rendszerekkel is dolgozni, mert sok szabványnak, eszköznek, jövőnek, stb-nek meg kell felelni
	- fontos úgy tervezni hálózatot, hogy fejleszthető/bővíthető legyen
	- **integrált átvitelt** érdemes kivitelezni, pl: pl különböző típusú átvitelekhez különböző hálózati megoldások voltak használva, pl: régi kábeles telefon, meg a mai mobiltelefonok.
		- az **Integrált** hálózatnál nincs különböző kivitelezés, a kivitelezés minél több készülékkel működjön
		- pl: 8.5 km réz kábelt a telefonnak, akkor ne legyen még külön 8.5 km réz kábel az internetnek, hanem az működjön mindakettővel == fele annyi kábel költség
- nem érdemes újra feltalálni a spanyol viaszt, inkább újra felhasználni a viasz elméletét, a te esetedre
### kapcsolati hálózat hierarchiája
- **elérési** **réteg**
- **elosztási** **réteg**
- **központi** **réteg**
	- **tűzfal**
	- **internet**
<img src="assets/halozat_acces_layer.png">
![[halozat_acces_layer.png]]

# 2. óra (2022.09.07)

### kapcsolt hálózat tervezési elemei
- **Hierarchia:** Megkönnyíti a kölönböző rétegek közötti eszközök szerepének megkülönböztetését. Csökkenti a hibatartományt.
- **Modularitás:** Hozzájárul a hálózat zökkenőmentes bővítéséhez.
- **Alkalmazkodó képesség:** Teljesíti a hálózat iránti felhasználó elvárásokat, az új eszközök is működjenek a régivel,
- **Rugalmasság:** Engedélyezi a forgalom intelligens terheléselosztását --> olyan hálózat kell, ami a hálózati terhelés változásakor legalább közepes mértékben tud automatikusan idomulni. --> pl: igények alapján kell választani eszközöket, és a legrugalmassabbat érdemes választani ami működik a legtöbb igénnyel. 
- *ezek az elvek erősen össze vannak kötve, egy ideális hálózatban mindegyik fontos.* 
<img src="assets/layerek_halozat.png" height="50%">
![[layerek_halozat.png]]
<img src="assets/halozat_layer2.png" height="50%">

![[halozat_layer2.png]]
### Hálózati rétegek mélyebben
<img src="assets/konvergens_halozati_reteget_melyebben.png">


### A kapcsolt hálózatok funckiói
 - A szolgáltatás minőségének biztosítása (Qos)
 - kiegészítő biztonsága
 - vezeték nélküli megoldások támogatása 
 - új technológiák beépítése

### Milyen jellemzőket kell nézni egy switchek kiválasztásánál
- **ár**
- **port sűrűség** --> hány port van az adott kapcsolón
- **energia használat** 
- **megbízhatóság**
- **portok gyorsasága** --> gigabites, vagy csak fast ethernet
- **átküldhető keretek mérete (frame buffer)** -->
- **skálázhatóság** (scalability) --> pl: egymásra tehető-e (stacking), vagy vagy összeköthető-e. 
<img src="assets/stackelt_switch.png">

### Kerettovábbítás
- azt hogy hogyan cselekszik, a **bemenő port** és a **célcím** alapján dönti el, hogy melyik porton fogja az adatot tovább küldeni
- minden hálózati kártyának egyedi azonosítójának kell lennie
<img src="assets/switch_portok_cucc.png">
![[switch_portok_cucc.png]]

#### Mac cím tábla
-  tele van a routerhez kapcsolódó eszközök mac-címével, amiket az eszköz csatlakozásánál ment le
- be lehet állítani, hogy mennyi idő után törölje a sok ideig nem használt eszközök mac címét, pl: 4 hét
- MAC tábla = CAM tábla
- új MAC-cím esetén, kiküldi össze portjára, hogy kié lehet ez a MAC cím --> **elárasztás** --> pl: géza a gyereked ott van 8 kisgyerekkel, és bekiabálsz hogy géza gyere már. ie: mindenki halja

#### Tárol és továbbit
- tárol-és-továbbít módszer esetén a kapcsoló csak akkor hoz továbbítási döntést, ha már a teljes keretet beolvasta és elvégezte rajta a hibaellenőrzést is (cyclic redundancy check, CRC).

#### Közvetlen kapcsolási módszer
- Ezzel ellentétben, a közvetlen kapcsolási mód esetén már a beérkező keret cél MAC-címének beolvasása és a kimenő port meghatározása után elkezdődik a továbbítási folyamat.




# 3. óra (2022.09.08)
### tárol és továbbit hiballenőrzés 
- minden bejövő kereten hibaellenőrzést hajt végre
- A teljes keret beérkezése után a kapcsoló összehasonlítja az adategység utolsó mezőjében található ellenőrző összeget (frame-check-sequence, FCS) a saját maga által kiszámított FCS értékkel (lásd store-and-forward-switching ábra alul)
- A művelet segítségével biztosítja, hogy a keret mentes a fizikai és adatkapcsolati hibáktól. Ha a keret hibamentes, a kapcsoló továbbítja, egyébként pedig eldobja azt.
<img src="assets/store_and_forward_switching.png">
![[store_and_forward_switching.png]]

### Töredékmentes továbbitás (fragment free forwarding)
- A töredékmentes továbbítás a közvetlen kapcsolás módosított változata, amikor a kapcsoló megvárja az ütközési ablak (64 bájt) beérkezését a keret továbbításának megkezdése előtt. Ez azt jelenti, hogy minden keret első része (az adattartalomig bezárólag) ellenőrzésre kerül töredezettség szempontjából. A töredékmentes továbbítási módszer jobb hibaellenőrzést biztosít, mint a gyorstovábbítás, és gyakorlatilag nem növeli a késleltetést.
- ez a gyorstovábbítás és a "tárol és továbbit" módszer közötti módszer, van rajta ellenőrzés, de gyorsabb is mint a "tárol és továbbít"

### Gyorstovábbítás (rapid frame forwarding)
- közvetlen kapcsolás esetén a továbbítási döntés a cél MAC-cím beérkezése után azonnal meghozható, a kapcsolónak nem kell megvárni a keret további részeinek megérkezését.

### Ütközési tartományok
<img src="assets/hal_duma.png">
![[hal_duma.png]]
<img src="assets/utkozesi_tartomany.png">
![[utkozesi_tartomany.png]]

### Hálózati túlterhelés enyhítésén segít:
- **nagy port sűrűség**
- **nagy portsebesség**
- **gyors belső kapcsolás**
- **nagy puffer méret**
- **alacsony portonkénti kölcség** --> nem mindegy hogy van egy 50-ezres switch 8 porttal vagy egy 600-ezres switch, de 120 porttal.

switch alapkonfiguráció: 
- 


# 4. óra (2022.09.12)
dolgozatban: - router kezdeti beállításai

<img src="assets/kapcsolo_kezdeti_beallitasai.png">
![[kapcsolo_kezdeti_beallitasai.png]]

### Állapot jelzések
<img src="assets/allapotjelzok.png">
![[allapotjelzok.png]]

<img src="assets/switch_allapotjelzesek_kep.png">
![[switch_allapotjelzesek_kep.png]]

**SVI (Switch virtual interaface)** - virtuális kapcsoló interface

<img src="assets/Switch_management_interfesz.png">
![[Switch_management_interfesz.png]]

<img src="assets/switch_default_gateway.png">![[switch_default_gateway.png]]
<img src="assets/switch_management_verify.png">
![[switch_management_verify.png]]

<img src="assets/duplex_speed_config.png">
![[duplex_speed_config.png]]

### Ellenőrzések
<img src="assets/veryfication_commands.png">
![[veryfication_commands.png]]

<img src="assets/interface_status.png">
![[interface_status.png]]

<img src="assets/running_config.png">
![[running_config.png]]

<img src="assets/Network_access_layer_issues.png">![[Network_access_layer_issues.png]]

<img src="assets/troubleshooting_switch_media_issues.png">
![[troubleshooting_switch_media_issues.png]]

<img src="assets/ssh_config.png">
![[ssh_config.png]]
- ssh-hoz mindig kell egy domain név és minimum 1024-es rsa kulcs, ás át kell telnetről az ssh-ra transportálni (transport input ssh) , és még esetleg ssh ver 2-re átállítani
- *ha esetleg valamiért vissza akarnál állni telnetre, akkor (transport input telnet)*

<img src="assets/ssh_a_puttyban.png">
![[ssh_a_puttyban.png]]

<img src="assets/ssh_tavoli_kapcsolat.png">
![[ssh_tavoli_kapcsolat.png]]

<img src="assets/veryfiy_ssh_status.png">
![[veryfiy_ssh_status.png]]

### DHCP-kiéheztetés
<img src="assets/dhcp_kieheztetes.png">
![[dhcp_kieheztetes.png]]

### CDP (cisco discovery protocol) 
- vigyázni kell vele, mert támadók potenciálisan ki tudják használni, ha nem jol kezeljül --> nem érdemes használni 

### bevált biztonsági módszerek
<img src="assets/bevalt_biztonsagi_modszerek.png">
![[bevalt_biztonsagi_modszerek.png]]
<img src="assets/Security_consideration.png">
![[Security_consideration.png]]

### NTP (network time protocol) configuráció
- pontos időt hostolja, hogy mindegyi eszközön az idő ugyan az legyen.
- beállítod az időt, időzonát a host device-on
- és NTP-t configurálod, és beállítod a többi eszközön
<img src="assets/NTP_config.png">
![[NTP_config.png]]
<img src="assets/NTP_verifying.png">
![[NTP_verifying.png]]

# 5. óra (2022.09.14)
## Vlanok ismétlése
- **miért alkalmazunk vlan-okat?:
	- vele lehet kissebalhálózatokra osztani a hálózatokat
	- fontos , mert kisebb hibatartományokra lehet osztani, a hálózatot, hiba esetén könnyeb javitani
	- külön vlan legyen mindenféle osztálynak pl: hr, dolgozók, rendszergazda stb.
	- biztonságosabb, ha elvannak szeparálva a csoportok
	- kölcség szempontból olcsóbb lehet
	- teljesítmény jobb lehet 
	- rendszergazda csapat hatékonyságát növeli
	- könyebb menedzselni a hálózatot, embereket stb.

<img src="assets/vlan_groupok.png">
![[vlan_groupok.png]]
### Vlan-ok csekkolása
 <img src="assets/vlan_csekkolása.png">
 ![[vlan_csekkolása.png]]
#### Alapértelmezett vlan
már ide vannak alapból rendelve a portok, és egy új vlannál csak át huzzuk ezeket


### VoIP (voice over IP)
**fontos dolgok a VoIP-hoz**
- minimum sávszélességnek meg kell lennie
- prioritási sorrendet kell tudnia építeni
- a torlódásokat képesnek kell lennie elkerülni
- max 150 ms késleltetés legyen, mert utána már kényelmetlen kommunikálni

### VLAN trunk-ölése
<img src="assets/Vlan_mezo_cimkek.png">
![[Vlan_mezo_cimkek.png]]

### Vlan tartományok
<img src="assets/vlan_tartomanyok.png">
![[vlan_tartomanyok.png]]

<img src="assets/create_and_check_Vlans.png">
![[create_and_check_Vlans.png]]

<img src="assets/assing_ports_to_vlans.png">
![[assing_ports_to_vlans.png]]

##### Vlan interface csekkolás
<img src="assets/vlan_interface_verification.png">
![[vlan_interface_verification.png]]

<img src="assets/delete_vlan.png">
![[delete_vlan.png]]

#### **Display the switchport information for F0/18.**
- S1# show interfaces F0/18 switchport
- Name: Fa0/18  
- Switchport: Enabled  
- Administrative Mode: static access  
- Operational Mode: down  
- Administrative Trunking Encapsulation: dot1q  
- Operational Trunking Encapsulation: native  
- Negotiation of Trunking: Off  
- Access Mode VLAN: 20 (Students)  
- Trunking Native Mode VLAN: 1 (default)  
- Voice VLAN: none

<img src="assets/trunking.png">
![[trunking.png]]

<img src="assets/veryfing_trunking.png">
![[veryfing_trunking.png]]

### DTP (Dinamikus trunk protokol)
- cisco specifikus fos, nem kell, nem ajánlott használni
<img src="assets/DTP_fosok.png">
![[DTP_fosok.png]]

<img src="assets/DTP_interface_modes.png">
![[DTP_interface_modes.png]]

### Vlan-ok elleni támadások
- **Vlan Ugrás támadás (switch spoofing attack)** - A vlan ugrást használja ki 
- **kettős cimkézésből eredő ugrásos támadás** - 
<img src="assets/kettos_cimkes_ugras_vlan_attack.png">
![[kettos_cimkes_ugras_vlan_attack.png]]


# 6.óra (2022.09.19)
## A forgalomirányítás alapjai
-  *ha két hálózatot össze akar valaki kötni ahhoz kell egy router* 

<img src="assets/Network_characteristics.png">
![[Network_characteristics.png]]
<img src="assets/network_characteristics_magyarul.png">
![[network_characteristics_magyarul.png]]

- **router confignál alap dolgok**
- hostname-elni alap
- interfaceket descriptionelni alap --> valós hálózatokban beleirod az információkat, pl , mire kell, honnan hova, melyik teremben van, melyik épületben stb.
- minimum a három szokásos szintet jelszavazva alap
- crypto key gen, és minium 1024-es legyen de inkább több
- bekötött portok cimzése, bekapcsolása, nem használt portok lekapcsolása
- blokkolások configje, pl login block, jelszó többszörös elrontása után stb.
- tétlenség kezelése, pl 2 perc no használat után ujra kérjen logint

- **router feladati**
	- legrövidebb út tervezésem kezelése
	- továbbítás

- **csomagtovábbító módszerek**
	- Folyamatkapcsolás (Process switching) - a célcím alapján küldi tovább az adatot ie: terelgetés
	- Gyorskapcsolás (Fast switching) - nem foglalkozik nagyon a jó út megtalálásával csak kiküldi valamelyik portják ie: tologatás --> majd a következő router megoldja
	- Cisco Express Forwarding (Cisco Expressz Továbbítás, CEF) - cisco-s fos, nem kell használni

- **Otthoni vagy kis irodai eszközök csatlakozási módjai:**
	-   Laptopok és tabletek vezeték nélkül kapcsolódnak az otthoni forgalomirányítóhoz.
	-   A hálózati nyomtató Ethernet kábellel kapcsolódik az otthoni forgalomirányító kapcsolóportjához.
	-   Az otthoni forgalomirányító a szolgáltató kábelmodeméhez Ethernet kábellel kapcsolódik.
	-   A kábelmodem pedig az internetszolgáltató (Internet Service Provider, ISP) hálózatához kapcsolódik.
	
- **Ahhoz, hogy hozzáférjenek a hálózathoz, az eszközöknek a következő IP-cím információkkal kell rendelkezniük:**
	-   **IP-cím** - Egyedileg azonosít egy állomást a helyi hálózaton.
	-   **Alhálózati maszk** - Meghatározza az állomás helyi alhálózatát.
	-   **Alapértelmezett átjáró** - Meghatározza, hogy melyik forgalomirányítónak kell a csomagot küldeni akkor, ha a cél nem ugyanazon az alhálózaton van.


- **kell:**
	-   Az eszközök nevei
	-   A használt interfészek
	-   IP-címek és alhálózati maszkok
	-   Alapértelmezett átjárók címei
	-   **Topológia diagram** - Vizuális áttekintést ad a fizikai kapcsolatokról és a logikai harmadik rétegbeli címzésről. Legtöbbször valamilyen megfelelő programmal készítik, ilyen lehet a Microsoft Visio.
	-   **Címtáblázat** - Olyan táblázat, melyben az eszközök nevei, interfészei, IPv4-címei, alhálózat maszkjai és alapértelmezett átjárói szerepelnek.
<img src="assets/documenting_networking_adresses.png">
![[documenting_networking_adresses.png]]

- **Egy állomás az IP-cím információit kaphatja:**
	-   **Statikusan** - Az állomás IP-címét, alhálózati maszkját és alapértelmezett átjáróját kézzel állítják be. A DNS-szerver IP-címét szintén be lehet állítani.
	-   **Dinamikusan** - Az IP-cím információkat egy szerver biztosítja DHCP protokollal. A DHCP-szerver érvényes IP-címet, alhálózati maszkot és alapértelmezett átjárót ad a végberendezéseknek. A szerver ezeken felül egyéb információkat is átadhat még.

- **A konzol hozzáféréshez szükséges:**
	-   **Konzolkábel** - RJ-45 - DB-9 konzolkábel
	-   **Terminálemulációs szoftver** - Tera Term, PuTTY, HyperTerminal

<img src="assets/Switch_Vlan1_config.png">
![[Switch_Vlan1_config.png]]

- **A cisco router konfigurálása során a következő alapvető beállításokat kell először végrehajtani:**
	-   **Eszköz elnevezése** - Megkülönbözteti az eszközt többi forgalomirányítótól.
	-   **Hozzáférés biztonságossá tétele** - Biztonságossá kell tenni a privilegizált és felhasználói módot, a Telnet hozzáférést, és a legmagasabb szintű jelszótitkosítást kell beállítani.
	-   **Beállítani a belépési üzenetet** - Figyelmeztetés az engedély nélküli hozzáférésről

<img src="assets/jelszavazás.png">

##### Router alapkonfig
- **Enter the commands to configure the name of the router as 'R2'.**
- Router# configure terminal
- Enter configuration commands, one per line. End with CNTL/Z.
- Router(config)# hostname R2
- **Configure 'class' as the secret password.**
- R2(config)# enable secret class
- **Configure 'cisco' as the console line password and require users to login. Then exit line configuration mode.**
- R2(config)# line console 0
- R2(config-line)# password cisco
- R2(config-line)# login
- R2(config-line)# exit
- **Configure 'cisco' as the vty password for lines 0 through 4 and require users to login.**
- R2(config)# line vty 0 4
- R2(config-line)# password cisco
- R2(config-line)# login
- **Exit line configuration mode and encrypt all clear text passwords.**
- R2(config-line)# exit
- R2(config)# service password-encryption
- **Enter the banner 'Authorized Access Only!' and use # as the delimiting character.**
- R2(config)# banner motd #Authorized Access Only!#
- **Exit global configuration mode and save the configuration.**
- R2(config)# exit
- R2# copy running-config startup-config
- Destination filename [startup-config]?  
- Building configuration...  
- OK
- R2#  
- **You successfully configured R2 with initial settings.**


<img src="assets/intg00config.png">
![[intg00config.png]]


#### Loopback interface config
<img src="assets/loopback.png">
![[loopback.png]]

##### Command history csekkolása
<img src="assets/command_history.png">
![[command_history.png]]

<img src="assets/Packet_Forwarding_Decision_Process.png">
![[Packet_Forwarding_Decision_Process.png]]

- **néhány dinamikus protokollt az általuk használt mértékkel:**
	-   **Routing Information Protocol (RIP)** - Ugrásszám (hop count)
	-   **Open Shortest Path First (OSPF)** - A Cisco által használt költség a forrástól célig összegzett sávszélességen alapul.
	-   **Enhanced Interior Gateway Routing Protocol (EIGRP)** - Sávszélesség, késleltetés, terhelés, megbízhatóság

##### alapértelmezett gyorsaságok 
- a kevesebb jobb
- fontosak:
	- Belső EIGRP --> 90
	- statikus routing --> 1
	- RIP --> 120
	- OSPF -- >110
<img src="assets/Administrative_distances.png">
![[Administrative_distances.png]]

<img src="assets/A_Show_ip_route_mélyen.png">
![[A_Show_ip_route_mélyen.png]]

<img src="assets/routing_table.png">
![[routing_table.png]]

<img src="assets/network_entry_identifiers.png">
![[network_entry_identifiers.png]]
<img src="assets/network_entry_identifiers_magyarul.png">
![[network_entry_identifiers_magyarul.png]]

<img src="assets/Direcrtly_connected_network_entry_identifiers.png">
![[Direcrtly_connected_network_entry_identifiers.png]]

##### Statikus routing példa
<img src="assets/statikus_ip_routre_pelda.png">
![[statikus_ip_routre_pelda.png]]

<img src=assets/statikus_default_ip_route.png>
![[statikus_default_ip_route.png]]

<img src ="assets/supported_ipv6_routing_protocols.png">
![[supported_ipv6_routing_protocols.png]]

# 7. óra (2022.09.19)
### Vlanok közti forgalomirányítás
<img src="assets/inter_vlan_routing.png">
![[inter_vlan_routing.png]]

### Hagyományos vlan routing
<img src="assets/hagyomanyos.png">
![[hagyomanyos.png]]

<img src="router_on_a_stick.png">
![[router_on_a_stick.png]]

<img src="assets/switch_based_routing.png">
![[switch_based_routing.png]]

<img src="assets/hagyomanyos_vlan_routing_config.png">
![[hagyomanyos_vlan_routing_config.png]]

<img src="assets/router_on_a_stick_config.png">
![[router_on_a_stick_config.png]]

<img src="assets/configuring_router_on_a_stick_.png">
![[configuring_router_on_a_stick_.png]]

<<<<<<< Updated upstream
<img src="assetst/aron/asd1.png">
=======

# 8. óra (2022.09.21)
kezdés volt: netacad course: 6.1.1.2

<img src="assets/next_hop_router_router_config.png">
![[next_hop_router_router_config.png]]

<img src="assets/veryfing_tatic_routing.png">
![[veryfing_tatic_routing.png]]

<img src=assets/directly_connected_static_routing.png>
![[directly_connected_static_routing.png]]

<img src=assets/default_static_routing.png>
![[default_static_routing.png]]

<img src=assets/ipv6_unicast_routing.png>
![[ipv6_unicast_routing.png]]

<img src=assets/veryfing_ipv6_routing.png>
![[veryfing_ipv6_routing.png]]

<img src=assets/ipv6_next_hop_static_routing.png>
![[ipv6_next_hop_static_routing.png]]

<img src=assets/ipv6_static_directly_connected_routing.png>
![[ipv6_static_directly_connected_routing.png]]

<img src=assets/default_static_ipv6_route_syntax.png>
![[default_static_ipv6_route_syntax.png]]

<img src=assets/ipv6_default_static_route.png>
![[ipv6_default_static_route.png]]

<img src=assets/cim_osztalyok.png>
![[cim_osztalyok.png]]

<img src=assets/cim_osztyalyok_magyarazat_hun.png>
![[cim_osztyalyok_magyarazat_hun.png]]
6.3.1.3


>>>>>>> Stashed changes



