# 1. óra (2022.09.06)
### milyen dolgokra kell számítani?
- netacad.com --> kurzusok, amiket mészi adja. --> angol nyelvű főleg
- első félévbe 4 dolgozat lesz, a másikba 3 --> gyakorlati dogát, és az elmélet dogát űrlap formátumban, egressy-s email címmel
- szóbeli feleltetés nem lesz, csak ha valaki nem bir magával
- nem kéne késni
- netacadra lesz majd email invite

### hálózatok bevezetés
- biztonságnál is több emberre van osztva a munka, mert nem ismer mindenki mindent
- 100%-os biztonságot nehéz elérni, de minél közelebb kell jutni
- biztonság: informatikai rendszer esetén a működés mellett meg kell védeni az információk rendszeren kívülre jutását

##### fogalomak
- **biztonság**: pozitív oldalról közelíti meg --> ideális állapotot veszi figyelembe
- **kockázat**: ponthogy negatív oldalról közelíti meg --> veszélyeket veszi figyelembe --> felméri a potenciális károkat
- **kockázat elemzésről** van inkább szó
- a cél: a **kockázat csökkentése**
- **kockázat becslés** 
- **kliens szervermodell:** olyan számítógép, amely hozzáfér egy szolgáltatáshoz, amelyet egy számítógép-hálózathoz tartozó másik gép nyújt.
	- kérdéseket, lekérdezéseket küld a szervernek, 
	- választ fogad a szervertől
	- közvetlenül kommunikál a felhasználóval, általában GUI-val, de CLI-vel is

### biztonságos kommunikáció
- lényeg: két ember között alapkövetelmény hogy teljesen biztonságos legyen információ váltás

##### szakszavak
- **sértetlenség**: annak garantálása, hogy változás nélkül ér célba az elküldött üzenet, vagy egy esetleges hiba detectálható, vagy javítható pl: újraküldéssel
- **hitelesség**: a hitelesség a sértetlenségen felül, a vevő fél felé garantálja, hogy az adott üzenet a feltételezett küldőtől származik, és annak tartalma nem módosult. --> hitelesség = hitelesség + tájékozatás
- **letarthatatlanság**: tetszőleges harmadik személy felé is igazolható (pl: ügyvéd, bíró stb.), hogy az adott üzenetet a valódi küldő küldte.

# 2. óra (2022.09.08)
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
