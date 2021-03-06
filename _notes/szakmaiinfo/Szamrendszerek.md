# Számrendszerek
---

- több számrendszerről is lehet beszélni informatika terén
	- tízes
		- leggyakrabban használt számrendszer és számítástechnikás kívül is használva van
		- 0-tól 9-ig tartalmaz számokat 
		- másnéven tizedes számrendszer
		- számítástechnikában az egyik felhasználási területe, BCD kód (binárisan kódolt decimális)
		- a tízes számrendszerbe felírt számot számjegyenként binárisan kódoljuk, majd rendre egymás mellé írjuk a kapott számsorokat
	- kettes
		- másnéven bináris számrendszer
		- ez a számrendszer felel meg a számítógépes jelreprezentálásnak
		- két számot tartalmaz (0,1)
			- számítógépek mindent így tárolnak
		- úgynevezett végletes számrendszer, nincs köztes állapota ezért pontos értéket ad vissza, nincs véletlen fél bit
	- tizenhatos
		- másnéven hexadecimális számrendszer
		- byte szervezésű adatkezeléshez jobba illeszkedik
		- alapszáma a 16
		- tartalmaz 0-tól 9-ig számokat és A-tól F-ig betűket (10, 11, ... , 15)

---

### Kettes számrendszer igazságtáblák
- logikai műveletek kijelentését vizsgálja
- igazságtábláknak elnevezései vannak, ezek a logikai operátorok
	- AND (ÉS)
		- összekapcsolt állítások igazságértéke
		- igaz akkor ha mindkét állítás igaz
	- NAND (NEM ÉS)
		- pontos ellentetje az AND operátornak
		- igaz akkor ha mindkét állítás hamis
	- OR (VAGY)
		- igaz akkor ha legalább az egyik állítás igaz
	- NOR (NOT OR, NEM VAGY)
		- pontosan ellentetje az OR operátornak
		- amennyiben mindkét NOR-ral összekapcsolt feltétel vagy állítás hamis, az eredmény igazságértéke igaz lesz, minden más esetben viszont hamis.
	- XOR (kizáró VAGY)
		- igaz eredményt ad, amennyiben az összekapcsolt állításoknak vagy feltételeknek pontosan az egyike igaz.