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


# 2. óra (2022.09.12)
- **cryptográfia módszerek** - a kommunikáció lehallgatása esetén se tudja kiszedni belőle az információt a támadó --> mert le van titkosítva --> az információ lehallgatása után, még vissza kéne kódólni a titkosítást a titkos kulcs ismerete nélkül
	- a tiktosításnál fontos, hogy valószínűség alapján kis eséllyel tudja kitalálni a titkos kulcsot
- **távoli azonosítás** - elektronikusan végzett azonosítás --> már első alkalomtól tipikusan külső szereplő bevonásával kell megoldani --> a távoli azonosítás az elektronikus igazolványok rendszerével, illetve ezek hitelességét biztosító PKI (publikus kulcs infrastructúra)-kkel oldják meg.

### Biztonsági elvek
- **titkolózásra alapozott biztonság** - STO (Security through obscurity) --> valamiféle információ biztonságban tartása és fedése alapján működnek.
- **teljes közlés** - semmi biztonság --> szakmailag: semmit se szabad, csak azt amit külön engedélyezünk.
- **támadási módszerek** - pl: A támadó hasznot akar húzni a támadásból, vagy pl: kárt akar okozni, esetleg pl: a támadó arra akarja felhivni a figyelmet, hogy kiskapuk vannak a rendszerben (whitehat hacker). 
- **belső támadások** 
	- **FORK bomba** - rendszer hibán alapszik, és felzabálja a cpu-t és a ramot, erőforrás korlátozással lehet védekezni ellene.
	- **PUFFER túlcsordulás (puffer overload)** - ha túlírjuk a puffer méretet, abból problémák lesznek.
	- **ismert TEMP** - kihasználj az ideiglenes mappákat, és ezt kihasználva csinálnak valamit 
	- **exploit-ok** - előre gyártott programocskák, amelyek rendszergazdai jogköröket adhatnak az új hálózatba belépőknek --> kihasználták különféle programok biztonsági hibáit.
	- **SE (social engineering)** - nem biztonságosan használja a felhasználó a rendszert --> pl: illető ugyan azt a jelszót használja és egy fish attackba ellopják a jelszavát, és mindenébe be tud lépni --> emberek bizalomra hajlandóságát kihasználó technika
		- **adathalászat (fish attack)** - ellopják valami fontos adatodat pl: belépési adatok
- **külső támadások** 
	- **hamisítás alapjú támadások** - többségében úgy működnek, hogy az előre beállított protokolokat hamisítja, kihasználja.

# 3. óra (2022.09.14, 09.19)
- szolgáltatás lebénítás - DOS, DDOS attack
	- **merevlemez kapacitás felhasználása** - főleg webszerverek, levelezőszerverek, stb.
	- **számításkapacitás felhasználás** - terheli a host processzort 
	- **sávszélesség elleni támadás** - hasznos forgalmat haszontalan forgalommal szoritja ki - lassú lessz minden
	- egyéb 
		- DHCP kiéheztetés
		- switch-en MAC-cím tábla túlcsúrdítás
		- SYN flag (synchronisation flag) elárasztás  - ezzekkel a hamis kérésekkel árasztja el az eszközt
		- LAND attack (Local Area Network Denial attack) 
		- SMURF attack 
- **IPSEC** - internet security protocol
- **SIFFING** - hálózat forgalom megfigyelése
- **PORTSCAN** - portok scannelése 

### A védekezés külön módjai
- **belső támadások**
	- puffer túlcsordulás - normális implementálás
	- TEMP mappák, fájlok elleni kihasznál - ezek a fontos mappák dinamikusak legyenek --> esetleg x időszakonként, törlődik a mappa és a másik jön helyette
	- HIBA javítások és frissítések letöltése tartása - főleg security patchekre igaz
	- szerver támadások ellen - a legfontosabb adatokat, pótszervereken tárolni, pl fő szerver, pót szerver, és egy offline pót szerver
	- brute force - adott karakterkészletből pl 7 hosszú jelszó, végigpróbálja -> hatalmas mennyiségű próbálkozás, és idő --> megoldás loginblock
- **külső támadások **
	- fontos
		- követjük az adatforgalmat
		- titkosítjuk az adatkapcsolati hálózatokat
		- rendszeresen ellenőrizzük a nyitott portokat
		- jelszavazzuk, login block, login timeout stb beállítása
	- snifferek ellenőrzése --> általában úgy néz körül hogy az egész hálózatot pingelgeti
		- SYN flag --> used to initiate connection
		- FIN flag --> terminates connection
	 - Távoli operációs rendszerek vizsgálása (újlenyomat)
		 - megtudni a vizsgált illető milyen operációs rendszert fut -->

- **Naplózás**
	- A hálózatunkban történt eseményeket, pontos időbélyeggel, fontos információval naplózni --> ha bármi hiba van, vagy támadás ér, könnyeb helyrehozni
	- fontos: milyen információt naplózzunk, és milyen sűrűséggel --> ha minden dolgot naplózunk a saját rendszerünket bénítjuk le, kell egy egyensúj
	- figyelni kell: x idő után a naplófálj betelítse a tárhelyet
	- fontos naplózni: 
		- minden hálózatba és ból való kilépést, a sikerest és a sikertelent is --> sok információ van benne: pl elírásból való, vagy támadásból való stb stb
		- erőforrás használat
		- dhcp kiosztások
- **mindenből a secure verziót használjunk** 
	- SSL/TLS - A type of digital security that allows encrypted communication between a website and a web browser
	- HTTPS 
	- TPS
	- POP3S

- SSL kézfogás --> kulcsoknak rendezése
	- **pre master secret** --> 384 bites véletlen szám --> a kliens hozza létre --> titkosítja a szerver nyilvános kulcsával, és elküldi a szervernek --> a server megpróbálja decodolni a saját kulcsával --> ha sikerül akkor ő is megtudta a pre master secretet --> ebből lesz meg a master secret
	- **master secret** --> 48 byte-os titkosított adatcsomag --> master secretből lesz egy session key 
	- **session key** -->ez lesz a kulcs amit a kliens meg a szerver használni fog egymással

# 4.óra (2022.09.21)
SSL kézfogás 
- a kliens **elküldi** a szervernek az **SSL protokoll verzió számát**, egy **viszony azonosító számot**,  az **általa használni kívánt titkosítási paramétereket** és a **tömörítési módszert** (4 dolog)
- A szerver **válaszként** elküldi a **saját SSL protokoll verzió számát**, a viszony azonosítót, a saját titkosítási beállításait, a saját tanusítványát (4 dolog)
- A **kliens** megpróbálja **hitelesíteni** a **szervert** (ha nem sikerül akkor vége a folyamatnak)
- A **kapott** adatok **alapján** a **kliens** **generál** egy **pre master secretet**, ezt **kódolja** a **szerver** **nyílvános** **kulcsával** és végül ezt a **titkosított értéket elküldi** a szervernek
- A szerver a saját titkos kulcsával, dekódolja a pre master secret értékét és ezt felhasználva létre hoz egy master secret értéket
- mind a kliens mind a szerver létre hozzák a viszony kulcsokat, egy közös algoritmus alapján (ezek szimetrikus kúlcsok, amiket az üzenetek titkosítására, és az adatok sértettlenségének biztosítására vannak használva)
- Kliens --> Szerver : A kézfogás a részéről befejeződött
- Szerver --> Kliens : A kézfogás az ő oldaláról is kész

# A szerver hitelesítése
**A szerver tanusítvány tartalma**
	-  szerver nylvános kulcs
	- A szerver neve
	- A tanusítvány érvényesség ideje
	- A tanusítvány kiállítójának a neve (CA)
	- A kiállító digitális aláírása
**A kliens által karban tartott lista a megbízhatónak tartott CA-k ról**
	- A kiállító neve
	- A nyílvános kúlcsa
	- A digitális aláírása
**A sikeres hitelesítés részei**
	- Adott pilanatba a szerver tanusítványának érvényességének ellenörzése
	- A CA-nak a neve, benne kell lennie a megbízhatósági listájába
	- A listában szereplő nyílvános kulcs segítségével, ellenőrizhető legyen a CA digitális aláírásának érvényessége
	- A szerver tanusítványában szereplő neve meg kell egyezen a kliens által aktuálisan ismert szerver névvel (Ezzel próbálják kivédeni a közbe ékelődést)
	- Ezután a sikeres hitelesítéssel mehet tovább az SSH folyamat
## A kliens hitelesítése##
**A kliens tanusítványának részei**
	- A kliens nyílvános kulcsa
	- A kliens neve
	- A tanusítványának érvényességének ideje
	- A CA neve
	- A CA digitális aláírása

# Forgalomszűrés hozzáférési listák használatával
## Biztonság
A vállalati hálózaton belül a biztonság alapvető fontosságu
		-