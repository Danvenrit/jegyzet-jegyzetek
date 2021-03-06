# Átviteli közegek
---

- vezetékes
	- csavart érpár
		- két szigetelt, egymásra spirálisan felcsavart rézvezeték
	- koaxális kábelek
		- egy belső vezető érből, dielektrikumból, fémhálóból és külső szigetelésből áll
	- üvegszálas kábelek
		- Az információ fényimpulzusok formájában terjed egy fényvezetõ közegben, praktikusan egy üvegszálon
- vezeték nélküli
	- infravörös, lézer
	- rádióhullám
	- szórt spektrumú sugárzás
	- műholdas átvitel
	- bluetooth

---

### Vezetékes adatátvitel
- UTP (Unshielded Twisted Pair(árnyékolatlan csavart vagy sodrott érpár))
	- két szigetelt sodrott érpár
	- kategóriák
		1. kategória: hang minőségű átvitel (telefon vonalak)
		2. kategória: 4 Mbit/s sebességű átviteli képes vonal (helyi beszélgetés)
		3. kategória: 10 Mbit/s sebességű átviteli képes vonal (Ethernet)
		4. kategória: 20 Mbit/s sebességű átviteli képes vonal (16 Mbit/s Token Ring)
		5. kategória: 100 Mbit/s sebességű átviteli képes vonal (Fast Ethernet)
	- általában 4 csavart érpárt tartalmatznak a kábelek
	- árnyékolással a zaj csökkenthető 
- STP (Shielded Twisted Pair(árnyékolt csavart vagy sodrott érpár))
	- két szigetelt sodrott érpár árnyékoló fémszövettel
- koaxális kábelek
	- 
	- típusai
		- alapsávú -> 0 - 4 kHz beszédsáv, digitális jelátvitelre
			- sebesség: 100 Mbit/s (1000 méteren belül)
			- BNC csatlakozó
		- szélessávú -> televíziós jelátvitel, analóg jelátvitelre
			- 300 - 450 MHz-es jelátvitelre
			- 2 db frekvencia (adó és vevő)
			- csatlakozók
				-  sorkapocs
				- BNC
				- RJ11
				- RCA
				- DB9
				- DB25
	- hullámellenállás szerinti típusok
		- 50 ohmos alapsávú
		- 75 ohmos szélessávú
		- 75 ohmos alap- és szélessávú
	- veszteségek
		- ohmos veszteségek
		- dielektrikumbeli veszteségek (sugárzás)
		- skin hatás
- üvegszálak, optikai szálak
	- fényforrás -> átviteli közeg -> fényérzékelő
		- a fényforrás lehet LED vagy lézerdióda
			- fényimpulzosok áram hatására 
		- fényérzékelő egy fotótranzisztor vagy fotódióda
	- vákony üvegszál
	- veszteség
		- féányveszteség
			- visszaverődés
			- csillapítás
			- határfelület átlépő fénysugarak

---

### Vezeték nélküli adatátvitel
- Infravörös, lézer átvitel
	- adó-vevő párok háztetőkön
	- teljesen digitális
	- jól irányított
		- emiatt teljesen védett
	- zavar lehet az eső, köd, legköri szennyeződések
	- IrDA szabvány
- rádióhullám
	- nagyobb távolságok 
	- mikrohullám
	- 2-40 GHz közötti frekvenciatartomány
	- parabola - vevőantenna
		- sugárnyalábok
		- száz kilóméteres átfogás
	- reléző állomások
	- zavar lehet a vihar, villámlás és a legköri szennyeződések
	- a frekvenciakiosztás hatósági feladat
- Szórt spektrumú sugárzás
	- kisebb, lokális hálózatok
	- széles frekvenciasáv
		- normális vevő zajnak érzékel
	- a vevő felismeri is fogja az adást
	- antennaként megfelel egy vezeték
- műholdas átvitel
	- műholdakon lévő transzponder
		- a kapott jelet más frekvencián visszasugározzák
		- hogy a földön lévő antennákat ne kelljen mozgatni
	- földről állónak látszanak
	- 90 geostacionárius műhöld 4 fokonként
	- frekvenciatartományok
		- lefelé 3.7 - 4.4 GHz
		- felfelé 5.925 - 6.425 GHz
	- álltalában 500 MHz-es sávszélesség
	- késleltetés
		- 250 - 300 msec.