# Vzorce - *expressions*

- [MZCHÚ](https://data.nature.cz/ds/1)

# obsah hodiny:

## úvod do vzorců - expressions
- editace atributů v tabulce pomocí kalkulátoru polí - *Field calculator*
  - tvorba nového sloupce nebo aktualizace
- zápis vzorců 
  - funguje jako kalkulačka 
  - lze využívat funkce, které jsou dostupné v zobrazeném seznamu
  - lze se odkazovat na konkrétní sloupce a jejich hodnoty
  - zápis hodnot - syntaxe
	- čísla - `123`
	- text - `'les'`
	- sloupec - `sloupec` (nebo `"sloupec"`) - `"` je nutné použít, pokud název sloupce obsahuje mezery nebo speciální znaky
	- `$` - vrací výsledky na základě každého prvku zvlášť, např. `$area` - výpočet plochy prvku, `$perimeter` - výpočet obvodu prvku, `$length` - délka linie, `$id` - unikátní identifikátor prvku
	- `@` - proměnné - mohou být na různých úrovních, proměnné projektu, proměnnné symbologie, proměnné vrstvy, nebo i prvku (např. `@geometry`)
  - vzorce jsou využitelné na více místech v rámci QGIS
    - editace atributů - výpočet/aktualizace nových sloupců a hodnot
    - výběr pomocí vzorců - atributové dotazování
    - symbologie - psaní pravidel pro kategorie
    - tvorba popisků - příklad spojování textu
    - ovládání parametrů - *Data defined override* 
    - a další (generování geometrií pro vlastní symboly, ovládání mapových výstupů, analýzy...)
- příklady:
  - vytvoření nového sloupce s názvem `rozloha_ha` - výpočet rozlohy v hektarech 
     - `$area/10000`
  - vytvoření popisku, který obsahuje název, kategorii a rozlohu - 
```
'název: ' || NAZEV ||'\n'|| 
'kategorie: ' || KAT ||'\n'|| 
'rozloha: ' || rozloha_ha || ' ha'
```

### třetí úroveň
asdasdyxcyxc


## výběr pomocí vzorců - atributové dotazování

- analytická metoda pro výběr prvků dotazováním - výběr na základě dotazu na vlastnost vrstvy (výpočet, nebo testování atributu)
- pro základní atributové dotazování lze použít jednodochý formulář - *Select Features By Value...* (`F3`)
    - rychlé, vhodné pro jednoduché dotazy, používá pouze logiku `AND`, nelze použít další funkce, např. výpočet `$area` nebo `$perimeter`
- různé možnosti chování výběru - nový výběr, přidání do výběru, odebrání z výběru, vybrat ze stávajícího výběru ("podvýběr")
- použití vzorců pro výběr prvků - *Select By Expression...* (`Ctrl+F3`)
- v některých případech uživatelsky pomalejší, ale všestranné, lze kombinovat vzorce
- zadaný vzorec testuje každý prvek, jestli je výsledek pravda (`1`) nebo ne (`0`). Pokud je výsledek pravda, dá se prvek do výběru
    - příklady na vrstvě MZCHÚ
      - z vrstvy vyber pouze přírodní památky 
          - ```
            KAT ='PP'
            ```
      - z vrstvy vyber jenom chráněná území s rozlohou menší než 1 km2 
          - ```
            $area < 1000000
            ```

# Zdroje:
- [GISMentors - QGIS začátečník - Tvorba nových vrstev a jejich editace](https://training.gismentors.eu/qgis-zacatecnik/vektorova_data/editace.html#kalkulator-poli)

- [GISMentors - QGIS začátečník - Atributové a prostorové dotazování](https://training.gismentors.eu/qgis-zacatecnik/vektorova_data/dotazovani.html)

- [QGIS Documentation - Expressions](https://docs.qgis.org/3.34/en/docs/user_manual/expressions/expression.html) 
