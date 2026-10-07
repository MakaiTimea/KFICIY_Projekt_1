---
Name: Makai Tímea
Neptun: KFICIY
ID: 2026-LA-05
---

## Nyelvtanulási segéd egyéni haladáskövetéssel
A projekt célja egy adatbázis-központú, webes nyelvtanulási segéd megvalósítása, amely az angol idegen nyelv tanulását támogatja. A rendszer a tananyagelemeket, a felhasználók gyakorlási előzményeit és a tanulási eredményeket relációs adatbázisban tárolja, majd ezek alapján adatbázis-oldali logika segítségével meghatározza, hogy mely elemeket érdemes a következő gyakorlás során előtérbe helyezni. A felhasználó egy egyszerű webes felületen gyakorolhat, megtekintheti saját haladását, és visszajelzést kaphat a problémásabb tananyagelemekről.
## Célok
 -   **Elsődleges cél:** Egy működő, adatbázis-központú nyelvtanulási rendszer elkészítése, amely a korábbi teljesítmény alapján személyre szabott gyakorlási sorrendet állít össze.
 -   **Célfelhasználók / érintettek:** Idegen nyelvet tanuló felhasználók.
 -   **Mérhető sikerkritériumok:**
	 - A rendszer képes tananyagelemeket és felhasználói tanulási   
	   előzményeket kezelni.
	 - A gyakorlás során rögzíti a válaszokat és az   
	   eredményeket, majd ezek alapján adatbázis-oldali logika segítségével 
	   meghatározza a következő gyakorlási sort.
 -   **Technikai célok:** Legalább harmadik normálformának megfelelő adatmodell, adatbázis-oldali prioritásszámítás, két eltérő kiválasztási stratégia, összetett SQL lekérdezések és teljesítményoptimalizálás megvalósítása.
 -   **Korlátok:** Relációs adatbázis használata, legalább harmadik normálformáig kialakított adatmodell, adatbázis-oldali függvény vagy tárolt eljárás használata, valamint az adatbázisban megvalósított kiválasztási logika alkalmazása a felhasználói felületen.
## Hatókör
### Benne van a hatókörben
-   Felhasználók és tananyagelemek kezelése.
-   Szavak vagy kifejezések, jelentések, példamondatok, témakörök és nehézségi szintek tárolása.
-   Gyakorlási alkalmak, feladatok és felhasználói válaszok rögzítése.
-   A tanulási állapotok nyilvántartása és frissítése.
-   A válaszok helyességének, időpontjának és az ismétlések számának tárolása.
-   A tananyagelemek prioritásának kiszámítása korábbi eredmények alapján.
-   Legalább két eltérő gyakorlási sorrend-meghatározó stratégia megvalósítása.
-   A következő gyakorlási sor előállítása adatbázis-oldali logikával.
-   Összetett SQL lekérdezések készítése a tanulási eredmények elemzésére.
-   Reprodukálható tesztadatok generálása nagyobb mennyiségű tanulási előzménnyel.
-   Egyszerű webes felület a gyakorláshoz és a tanulási haladás megjelenítéséhez.
### Nincs benne a hatókörben
-   Összetett közösségi vagy kommunikációs funkciók.
-   Hanganyagok és kiejtésfeldolgozás az első verzióban.
-   Összetett mobilalkalmazás.
## Jegyzetek