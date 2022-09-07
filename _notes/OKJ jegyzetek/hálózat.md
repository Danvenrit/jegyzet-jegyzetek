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



