---
project_outline: [[00-project/01-project-outline]]
---

# Nyelvtanulási segéd egyéni haladáskövetéssel

## 1. Szereplők és jogosultságok

| Szerep | Igény | Hozzáférés |
|:---|:---|:---|
| Felhasználó | Angol szavak és kifejezések gyakorlása, saját haladásának követése. | Gyakorolja a tananyagot, válaszol a feladatokra és megtekinti az eredményeit. |
| Rendszeradminisztrátor | A tananyag kezelése, karbantartása. | Új tananyagelemeket, példamondatokat és témaköröket rögzít, illetve módosít. |

## 2. Use case-ek

### Személyre szabott gyakorlás

-   **Szereplő:** Felhasználó
    
-   **Előfeltétel:** A felhasználó megnyitotta az alkalmazást, és rendelkezik azonosítható felhasználói profillal.
    
-   **Fő folyamat:**
    
    1.  A felhasználó elindít egy gyakorlási alkalmat.
        
    2.  A rendszer az adatbázisban tárolt tanulási előzmények alapján kiválasztja a következő tananyagelemeket.
        
    3.  A rendszer megjeleníti a feladatot.
        
    4.  A felhasználó megadja a válaszát.
        
    5.  A rendszer ellenőrzi és eltárolja a választ, valamint annak helyességét és időpontját.
        
    6.  A rendszer frissíti a tanulási állapotot, és a gyakorlás végén megjeleníti az eredményeket.
        
-   **Alternatív / hibafolyamatok:** Ha a válasz üres vagy érvénytelen, a rendszer jelzi a hibát. Sikertelen mentés esetén a rendszer visszajelzést ad, és nem jelzi sikeresnek a mentést.
    
-   **Utófeltétel:** A gyakorlás eredményei az adatbázisban tárolódnak, és a következő gyakorlás kiválasztásánál is felhasználhatók.
    

### Tanulási haladás megtekintése

-   **Szereplő:** Felhasználó
    
-   **Előfeltétel:** A felhasználó rendelkezik korábban rögzített gyakorlási eredményekkel.
    
-   **Fő folyamat:**
    
    1.  A felhasználó megnyitja a haladás oldalát.
        
    2.  A rendszer lekéri a korábbi eredményeket.
        
    3.  A rendszer megjeleníti a helyes válaszok arányát, a gyakorlások számát és a problémásabb tananyagelemeket.
        
-   **Alternatív / hibafolyamatok:** Ha még nincs korábbi eredmény, a rendszer tájékoztatja a tanulót, hogy egyelőre nincs megjeleníthető adata.
    
-   **Utófeltétel:** A tanuló áttekintheti saját fejlődését.
    

## 3. Funkcionális követelmények

| Követelmény | Elfogadási kritérium | Prioritás |
|:---|:---|:---|
| A rendszer kezeli a tananyagelemeket és azok kapcsolatait. | A szavakhoz jelentések, példamondatok, témakörök és nehézségi szintek rendelhetők. | Kötelező |
| A tanuló gyakorlást indíthat. | A rendszer az adatbázisban tárolt tanulási előzmények alapján összeállít egy gyakorlási sort. | Kötelező |
| A rendszer rögzíti a válaszokat és az eredményeket. | Minden beküldött válaszhoz eltárolja a helyességet és a válasz időpontját. | Kötelező |
| A rendszer frissíti a tanulási állapotot. | A gyakorlás után frissül az adott tananyagelem ismétlésszáma és utolsó gyakorlási időpontja. | Kötelező |
| A rendszer legalább két kiválasztási stratégiát támogat. | Két eltérő stratégia használható, és eredményük összehasonlítható. | Kötelező |
| A tanuló megtekintheti a haladását. | A felület megjeleníti a gyakorlások eredményeit és a problémásabb tananyagelemeket. | Kötelező |
| A rendszer részletesebb statisztikákat jelenítsen meg. | A tanuló témakörönként vagy időszakonként is megtekintheti az eredményeit. | Ajánlott |
| A rendszer kezelje a megszakított gyakorlási alkalmakat. | Egy félbehagyott gyakorlás állapota egyértelműen megkülönböztethető a befejezett alkalomtól. | Ajánlott |

Prioritás: **Kötelező** = a projekt teljesítéséhez szükséges; **Ajánlott** = fontos, de nem alapfeltétel; **Lehetséges** = későbbi bővítés.

## 4. Üzleti szabályok és korlátok

| Szabály vagy korlát | Indoklás |
|:---|:---|:---|
| A rendszer egy választott idegen nyelv, jelen esetben az angol tanulását támogatja. | A projekt terjedelme így kezelhető marad. |
| Az adatmodellnek legalább harmadik normálformának kell megfelelnie. | Ez segít elkerülni a felesleges adatismétlést és az adateltéréseket. |
| A felhasználói válaszokat és a gyakorlási előzményeket meg kell őrizni. | Ezek szükségesek a tanulási állapot és a prioritás meghatározásához. |
| A gyakorlási sorrend meghatározása adatbázis-oldalon történik. | A felhasználói felület nem helyettesítheti saját algoritmussal az adatbázisban megvalósított logikát. |
| A kiválasztási logika legalább két stratégiát használ. | Így összehasonlítható, hogy a különböző megközelítések milyen eredményt adnak. |
| Az adatbázisban idegen kulcsok, egyediségi feltételek és megfelelő ellenőrzések biztosítják az adatok helyességét. | Megelőzi a hibás vagy egymásnak ellentmondó rekordok tárolását. |

## 5. Felhasználói felület és munkafolyamat

A rendszer egy egyszerű webes alkalmazásból áll. A fő felületek a gyakorlóoldal és a haladást megjelenítő oldal. A gyakorlóoldalon a tanuló megkapja a következő feladatot, megadja a válaszát, majd visszajelzést kap az eredményről. A haladás oldal a korábbi gyakorlások adataiból mutat összesítéseket.

A felhasználói felület az adatbázisban megvalósított logikát használja a következő gyakorlási sor lekéréséhez. Az adatbázis kezeli az adatokat, rögzíti az eredményeket, és elvégzi a prioritásszámítást. A webes felület feladata ezek megjelenítése és a felhasználói műveletek kezelése.

## 6. Nem funkcionális követelmények

| Követelmény | Ellenőrzés módja |
|:---|:---|:---|
| A rendszer normál használat során a gyakorlófeladatokat és az eredményeket elfogadható időn belül jelenítse meg. | A feladatbetöltés és a válaszmentés idejének mérése több teszt során. |
| A tanuló különösebb útmutatás nélkül el tudjon indítani egy gyakorlást és meg tudja tekinteni az eredményeit. | Egyszerű használhatósági teszt egy olyan személlyel, aki korábban nem használta az alkalmazást. |
| A hibás vagy sikertelen mentés ne jelenjen meg sikeres műveletként. | Hibás bemenetekkel végzett tesztek. |

## 7. Nyitott kérdések és kockázatok

| Kérdés / kockázat | Hatás | Felelős | Feloldás / döntés |
|:---|:---|:---|:---|
| Milyen szabályok alapján számítsuk a prioritást? | Befolyásolja a gyakorlási sorrendet és a módszerek összehasonlíthatóságát. | Hallgató | Egyszerű szabályalapú módszerrel kezdeni, majd súlyozott módszert is megvalósítani és tesztelni. |
| Hogyan biztosítható a megfelelő teljesítmény sok rekord esetén? | A lekérdezések és a prioritásszámítás lassúvá válhatnak. | Hallgató | Tesztadatokat generálunk, mérjük a lekérdezéseket, és szükség esetén indexeket alkalmazunk. |

## 8. Kezdeti technikai javaslat

### Javasolt megoldás

A rendszer egy egyszerű webes felületből, egy szerveroldali rétegből és egy Oracle relációs adatbázisból áll. A webes felület felel a gyakorlás megjelenítéséért és a felhasználói műveletekért. A szerveroldali réteg továbbítja a kéréseket az adatbázis felé. Az adatbázis tárolja a tananyagot és a gyakorlási előzményeket, valamint PL/SQL-eljárásokkal vagy függvényekkel kiszámítja a prioritásokat és előállítja a következő gyakorlási sort.

### Technológiai irány

| Terület | Jelölt technológia / megközelítés | Megfontolás oka | Nyitott kérdés / kockázat |
|:---|:---|:---|:---|
| Webes UI / Frontend | JavaScript alapú webes felület | Egyszerű, könnyen használható felület a gyakorláshoz és a tanulási haladás megjelenítéséhez. | A megfelelő keretrendszer kiválasztása és az adatbázisból érkező adatok megjelenítése. |
| Backend | Java vagy Python | A felhasználói műveletek kezelése és a frontend, valamint az adatbázis közötti kapcsolat biztosítása. | Az Oracle-adatbázissal való kapcsolat kialakítása és a hibás kérések kezelése. |
|Adatbázis / Tárolás | Oracle Database | Relációs adatmodell, összetett SQL-lekérdezések és nagyobb mennyiségű tanulási előzmény kezelése. | A táblák és kapcsolatok megfelelő kialakítása, valamint a lekérdezések teljesítményének optimalizálása. |