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
- minden
- 
- 
- bejövő kereten hibaellenőrzést hajt végre
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
