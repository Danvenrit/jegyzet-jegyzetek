# Állománytípusok
---

Az állomány a számítógép háttértárolóin lévő információ tárolási egysége. A fájlban tárolt adat tetszőleges. Lehet szöveg, kép, hang. 
A fájl valamelyik háttértárolón tárolt, névvel és kiterjesztéssel azonosított adategyüttes-
A fáljrendszer az operációs rendszer telepítésekor, meglévő kötetek formázásakor, vagy új merevlemezes telepítésekor választható ki.

---

### Fájlrendszerek
- FAT
	- egyszerű, robosztus
	- MS-DOShoz lett fejlesztve
- FAT32
	- FAT továbbfejlesztése
- exFAT
	- FAT legújabb verziója
- NFTS
	- Windows NT és utódjainak szabvány fájlrendszere
	- jogosultsági rendszer
	- működés közbeni állománytömöríté
- EXT
	- legújabb: ext4
	- Linux szabvány fájlrendszer

---

<img src="assets/faljfajtaktablazat.png">

Ha a fájl NFTS fájlrendszert használó meghajtón található, további biztonsági beállításokat is elvégezhetünk:
	- lehetőségünk van engedélyek kiadásáras
	- automatikus ki és betömörítés
	- titkosítás
	- indexelés
