# Mapové výstupy
## Data:
- ČÚZK Data50 - [ČÚZK Geoportal](https://geoportal.cuzk.cz/(S(adyuddkhlhhwkd4233mpxxdz))/Default.aspx?mode=TextMeta&side=mapy_data&metadataID=CZ-CUZK-DATA50-V&head_tab=sekce-02-gp&menu=22900)

## Příprava dat pro mapový výstup
- načteme potřebná data, a nachystáme  vzhled vrstve - symbologie, popisky atd. podle potřeby

!!! tip

    Pokud se jako první do QGIS přidá vrstva se souřadnicovým systémem WGS84 (EPSG:4326) tak se pro celý projekt nastaví tento souřadnicový systém (toto chování se dá změnit v nastavení QGIS). Pro zobrazení S-JTSK (EPSG:5514) je třeba zobrazení změnit tlačítkem s EPSG kódem vpravo na spodní liště. V našem případě se to stalo pokud do prázdného projektu přidáme pouze WMS ortofoto, které je nastavené tak, že přichází data ve WGS84.

## Layout (Mapový výstup, tiskové rozvržení):
- mapa pro tisk se tvoří v samostatném okně, kde lze nastavit vlastnosti papíru, a přidají se jednotlivé objekty - mapa, texty, měřítko, legenda, směrovka atd.

- nový *layout* se dá zapnout tlačítkem na liště, nebo z menu *Project -> New print layout...* (*Nové rozvržení tisku*), pro opětovné otevření mapového rozvržení potom *Layout manager* (*Správce rozvržení*)

- přidání jednotlivých prvků a popis jejich vlastností
    - *Add map* - mapové okno - měřítko, mřížka (grid)
    - *Add label* - text - styl, zarovnání, dynamický text (např. datum)
    - *Add North Arrow* - směrovka - svg, natočení
    - *Add Scale Bar* - měřítko - grafické vs číselné, nastavení jednotek, segmenty
    - *Add legend* - legenda - aktualizace vs ruční úprava
- export do .pdf, lze i do obrázku (.png, .jpg, ...) nebo .svg

## Úkol k procvičení
- vytvořte 
    - mapu s daty ČÚZK Data50 - vrstva *Hrady*
    - mapu chráněných území
  - nastavte vhodnou symbologii, popř. popisky, mapu vytvořte se všemi náležitostmi - název mapy, legenda, měřítko, směrovka,...

#### zdroje:
- [GISMentors - QGIS začátečník - Mapový výstup](gismentors.github.io/qgis-zacatecnik/mapovy_vystup/index.html)
- [QGIS Documentation - Laying out the maps](https://docs.qgis.org/3.40/en/docs/user_manual/print_composer/index.html#laying-out-the-maps)