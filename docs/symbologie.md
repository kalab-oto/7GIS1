# Symbologie a popisky 

## Data
- ukázka datového portálu AOPK ČR [https://data.nature.cz/](https://data.nature.cz/) a stažení vrstvy [Velkoplošná zvláště chráněná území](https://data.nature.cz/ds/3)

## Opakování
- načtení dat
- orientace v atributové tabulce

## Symbologie
- pomocí panelu stylování - Layer Styling (F7), nebo tlačítkem v hlavičce panelu vrstev (Layers) - potom záložka *Symbology*
    - symbologii lze také měnit ve vlastnostech vrstvy
- **Single (Jednoduchý) symbol**
    - princip tvorby jednoduchého symbolu
    - symbol se skládá z vrstev, které mohou být různého typu (Jednoduchá výplně, gradient, liniový vzor, bodový vzor, centroid atd.)
      - na nejnižší úrovni jde vždy o kombinaci základních typů - Fill (Výplň), Line (Linie), Marker (Značka)
- **Categorized (Kategorizovaný)**
    - pro nespojité proměnné - kategorie
    - podle zvolené hodnoty se v rámci vrstvy vytvoří jednotlivé kategorie
        - základní možnost je výběr atributu dostupného v atributové tabulce
    - na základě symbolu a barevného rozsahu se vytvoří jednotlivé symboly, které jde dále samostatně upravit
    - pro vytvoření kategorií slouží tlačítko *Classify* dole pod tabulkou
- **Graduated (Odstupňovaný)**
    - pro kontinuální proměnné - intervaly
    - funkce je obdobná jako u kategorizované symbologie
    - lze zobrazit histogram dat - v záložce histogram -> Load values (Načtení hodnot)
    - různé režimy tvorby tříd intervalů
    - intervaly lze ručně upravit buď přímo v tabulce, nebo pomocí histogramu

## Popisky (Labels)

- popisky prvků se zapínají a nastavují v panelu stylování (F7) v záložce *Labels*
- ukázali jsme si pouze možnost Single Labels
- hlavní položka pro vykreslování popisků je *Value*. Zde se určuje, co se zobrazí jako popisek
    - nejjednodušší možnost je výběr atributu, ale lze využít i vzorce
- popisky lze stylovat - barva textu, font, velikost písma, mezery mezi písmeny, slovy a řádky atd.
- lze nastavit vykreslení obalové zóny - *Buffer* nebo podkladu *Background*, stínování *Shadow* a vodící linky *Callouts* (přímá, zakřivená, Manhattan)
- automatické umístění popisků na základě obecného nastavení (okolo centroidu, po obvodu atd.)
- ruční umístění popisků - pomocí atributu a/nebo lišty popisků (*Move label...* ikonka s popiskem a šipkou)
    - při použití ručního posunu bez předchozího stanovení atributu QGIS vytvoří skrytý atribut uložený v rámci projektu (*auxiliary storage*). V takovém případě při prvním použití vyskočí okno, kde je nutné stanovit atribut nesoucí unikátní hodnoty, ke kterému se skrytý atribut připojí.

## Úkol k procvičení

- stáhněte si data Maloplošných zvláště chráněných území z [data.nature.cz](https://data.nature.cz/)
- nastavte symbologii podle typu MZCHÚ (kategorie)
- zjistěte, kolik územích je v každé kategorii
- vyzkoušejte
    - zjistěte, která NPR je největší (rozlohou)
    - Najděte přírodní rezervaci Grybla


## Zdroje
- [GISMentors - QGIS začátečník - Styl](https://gismentors.github.io/qgis-zacatecnik/vektorova_data/vektor_data_prace.html#styl)
- [QGIS Documentation - Symbology properties](https://docs.qgis.org/3.40/en/docs/user_manual/working_with_vector/vector_properties.html#symbology-properties)
- [QGIS Documentation - Layer Styling Panel](https://docs.qgis.org/3.40/en/docs/user_manual/introduction/general_tools.html#layer-styling-panel)
- [QGIS Documentation - Labels properties](https://docs.qgis.org/3.40/en/docs/user_manual/working_with_vector/vector_properties.html#labels-properties)