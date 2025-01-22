# Mapové výstupy
#### data:
- AOPK [https://data.nature.cz/](https://data.nature.cz/) Natura 2000 **Evropsky významné lokality (EVL)**

#### obsah hodiny:
##### opakování:
- změna symbolu polygonu, přidání WMS, změna souřadnicového systému
- tip: pokud se jako první do QGIS přidá vrstva se souřadnicovým systémem WGS84 (EPSG:4326) tak se pro celý projekt nastaví tento souřadnicový systém (toto chování se dá změnit v nastavení QGIS). Pro zobrazení S-JTSK (EPSG:5514) je třeba zobrazení změnit tlačítkem s EPSG kódem vpravo na spodní liště. V našem případě se to stalo pokud do prázdného projektu přidáme pouze WMS ortofoto, které je nastavené tak, že přichází data ve WGS84

##### Layout (Mapový výstup, tiskové rozvržení):
- nový layout se dá zapnout tlačítkem na liště nebo z menu *Project -> New print layout...*, pro opětovné otevření mapového rozvržení potom *Layout manager*
- mapa pro tisk se tvoří v samostatném okně, kde se nastaví vlastnosti papíru a přidávají se jednotlivé objekty - mapa, texty, měřítko, legenda, směrovka
- probrán popis okna rozvržení a princip tvorby mapy
- přidání jednotlivých prvků a popis jejich vlastností
  - *Add map* - mapové okno - měřítko, mřížka (grid)
  - *Add label* - text - styl, zarovnání, dynamický text (např. datum)
  - *Add North Arrow* - směrovka - svg, natočení
  - *Add Scale Bar* - měřítko - grafické vs číselné, nastavení jednotek, segmenty
  - *Add legend* - legenda - aktualizace vs ruční úprava
- export do pdf a png

#### zdroje:
- [GISMentors - QGIS začátečník - Mapový výstup](https://training.gismentors.eu/qgis-zacatecnik/mapovy_vystup/index.html)
- [QGIS Documentation - Laying out the maps](https://docs.qgis.org/3.34/en/docs/user_manual/print_composer/index.html#laying-out-the-maps)