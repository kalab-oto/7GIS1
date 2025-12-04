# Vzorce - *expressions*

## data
- ukázka datové sady [DIBAVOD](https://www.dibavod.cz/index.php?id=27)
  - práce s vrstvou *D05 - hranice aktivní zóny záplavového území pro Q100*

## úvod do vzorců (výrazů) - ε - expressions
- vzorce se v QGIS dají použít zaúčelem získání nových hodnot (např. výpočet rozlohy), nebo pro ověření podmínek (výběr na základě hodnot atributů)
- vzorce se dají využít v QGIS na více místech:
    - editace atributů - výpočet/aktualizace nových sloupců a hodnot
    - výběr pomocí vzorců - atributové dotazování
    - symbologie - psaní pravidel pro kategorie
    - tvorba popisků - spojování textu
    - ovládání parametrů - *Data defined override* 
    - a další (generování geometrií pro vlastní symboly, ovládání mapových výstupů, analýzy...)
- vzorce fungují jako kalkulačka, lze mimo jiné používat matematické operátory, logické operátory, funkce, podmínky, atd.
- k jednoduchému psaní vzorců slouží okno editoru vzorců (*Expression string builder*) a označuje se znakem ε (řecké písmeno epsilon)
  - lze využívat funkce, které jsou dostupné v zobrazeném seznamu
  - v seznamu lze také procházet a poklikáním přidávat do vzorce jednotlivé atributy dané vrstvy nebo hodnoty v těchto atributech
  - v právé části okna je vždy nápověda (popis a použití) k dané funkci
  - ve spodní části je náhled výsledku vzorce pro jednotlivé prvky
- zákaldní syntax
	- čísla - `123`
	- text - `'les'`
	- sloupec - `sloupec` (nebo `"sloupec"`) - odkáže na daný sloupec, `"` je nutné použít, pokud název sloupce obsahuje mezery nebo speciální znaky
	- `@` - proměnné - mohou být na různých úrovních, proměnné projektu, proměnnné symbologie, proměnné vrstvy, nebo i prvku (např. `@geometry`)
	- `$` - vrací výsledky na základě každého prvku zvlášť, např. `$area` - výpočet plochy prvku, `$perimeter` - výpočet obvodu prvku, `$length` - délka linie
    	- pouze pár funkcí

### Editace atributů
- tvorbu a editaci atributů v atributové tabulce můžeme provádět pomocí kalkulátoru polí - *Field calculator* 
- kalkulátor polí, umožní vytvořit nový sloupec (atribut) a do něj zaspat hodnoty na základě vzorce
  - lze zde také aktualizovat (přepsat) hodnoty v již existujícím sloupci, ale to lze provést i v samostatném panelu přímo v atributové tabulce bez použití kalkulátoru polí. Je možné aktualizovat buď všechny prvky, nebo jen ty vybrané

- příklady:
  - vytvoření nového sloupce s názvem `rozloha_ha` - výpočet rozlohy v hektarech 
     - ```
       $area/10000
       ```
  - vytvoení nového sloupce s názvem `rozloha2` - vynásobíme existující sloupec nějakým číslem
     - ```
       rozloha_ha * 2
       ```

### Výběr pomocí vzorců - atributové dotazování
- analytická metoda pro výběr prvků dotazováním - výběr na základě dotazu na vlastnost vrstvy (výpočet, nebo testování atributu)
- vzorec slouží jako podmínka pro výběr prvků - vzorec otestuje každý prvek, jestli splňuje podmínku, pokud ano výsledek je pravda (`1`) - dá se do výběru, pokud ne, výsledek je nepravda (`0`) - nedá se do výběru
- různé možnosti chování výběru - nový výběr, přidání do výběru, odebrání z výběru, vybrat ze stávajícího výběru ("podvýběr")
- použití vzorců pro výběr prvků - *Select By Expression...* (`Ctrl+F3`)

- příklady
  - vyber záplavová území s rozlohou větší než 100 ha
    - ```
      $area < 1000000
      ```
  - vyber záplavová území Ostravice
    - ```
      "NAZ_TOK" = 'Ostravice'
      ```
  - vyber záplavová území Ostravice a s rozlohou větší než 100 ha
    - ```
      "NAZ_TOK" = 'Ostravice' AND $area > 1000000
      ```
  - vyber záplavová území Ostravice a Odry
    - ```
      "NAZ_TOK" = 'Ostravice' OR "NAZ_TOK" = 'Odra'
      ```
    - nebo pomocí operátoru `IN`
    - ```
      "NAZ_TOK" IN ('Ostravice', 'Odra')
      ```  
- pro základní atributové dotazování lze použít i jednodochý formulář - *Select Features By Value...* (`F3`)
  - rychlé, vhodné pro jednoduché dotazy, používá pouze logiku `AND`, nelze použít další funkce, např. výpočet `$area` nebo `$perimeter`
- v některých případech může být tedy použití vzorců pro výběr prvků  pomalejší, ale je všestranné - umožňuje psát složité dotazy
 

### Kategorie ve vrstvě - symbologie podle kategorií
- v symbologii vrstvy lze využít vzorce pro tvorbu kategorií
- podobně jako u výběru prvků, vzorec otestuje každý prvek, a na základě výsledku (hodnoty) se přiřadí kategorie `1` nebo `0`
- např. `$area < 1000000`

### Popisky
- vytvoření popisku, který obsahuje název toku a jeho rozlohu 
```
'název: ' || NAZ_TOK ||'\n'|| 
'rozloha: ' || rozloha_ha || ' ha'
```
  - `||` - operátor pro spojování textů
  - `\n` - nový řádek, u popisků lze zalomení textu nastavit pomocí zalomení na specifickém znaku nastaveném v možnostech popisků


## Úkol k procvičení

- ve vrstvě MZCHÚ vyberete všechny přírodní památky (PP) z rozlohou větší než 200 ha 
- ve vrstvě MZCHÚ vyberete všechny přírodní památky (PP) a přírodní rezervace (NPP)

## Zdroje:
- [GISMentors - QGIS začátečník - Tvorba nových vrstev a jejich editace](https://gismentors.github.io/qgis-zacatecnik/vektorova_data/editace.html#kalkulator-poli)

- [GISMentors - QGIS začátečník - Atributové a prostorové dotazování](https://gismentors.github.io/qgis-zacatecnik/vektorova_data/dotazovani.html)

- [QGIS Documentation - Expressions](https://docs.qgis.org/3.40/en/docs/user_manual/expressions/expression.html) 
