# Rastrová data 

## Data:
DMT - digitální model terénu ČR - 100m - 
- datová sada ke Gismentors  [QGIS školení pro začátečníky](http://training.gismentors.eu/geodata/qgis/data.zip)
- jinak 5 m DMT - [DMR 4G ČÚZK GRID](https://geoportal.cuzk.cz/(S(t4galq2jkrjhwn3mlpqmyg4s))/Default.aspx?mode=TextMeta&side=vyskopis&metadataID=CZ-CUZK-EL&head_tab=sekce-02-gp&menu=304)
- Bioclim - [WorldClim](https://www.worldclim.org/data/bioclim.html)

## Úvod
- popis rastrových dat - co to je, jak se liší od vektorových dat
- pravidelná mřížka buněk - typicky obdelníky - pixely
  - souřadnicový systém - EPSG
  - *bounding box* - rohové souřadnice rastru - "obdelník"
    - *no data* - hodnota pro chybějící data
  - *cell size* - velikost buňky - rozlišení rastru
  - *height, width* - počet řádků a sloupců - počet buněk v rastru, když známe i bounding box získáme i rozlišení
- využití rastrových dat - analýza, vizualizace, modelování
- typy
  - spojité
    - družicové a letecké snímky 
    - naměřené, modelované hodnoty - nadmořská výška, teplota, srážky
  - nespojité - kategorie, třídy
    - typ území - landuse, landcover, kategorie půd, typy lesů
- pásma
- využití, družicové snímky, letecké snímky, data - modely
- princip mapové algebry

### DMT a základní vizulaizace
- pojmy DMT, DMT a DMR
- symbologie
  - Singleband gray - šedá stupnice
  - Singleband pseudocolor - barevná škála
    - Interpolation 
      - Linear - lineární interpolace barev gradientu mezi hodnotami
      - Discrete - pevné/ostré hranice barev podle hodnot
      - Exact - pevné hodnoty barev pro jednotlivé hodnoty - hodí se pro hledání pixelů s konkrétními hodnotami, nebo pro kategoriální rastry - zde je ale vhdonější použít kategorickou symbologii - Paletted/Unique values
    - Mode - generování hodnot pro barevnou škálu
  - lze i hillshade - stínovaný relief, v další části vytvoříme ale samostatný rastr
- základní analýza - *Raster -> Analysis*
  - slope - sklon
  - aspect - expozice svahu (hodnoty 0 až 360, podle orientace na světovou stranu)
  - hillshade - stínovaný relief
- další analýzy
  - Processing toolbox - zonální statistika - můžeme vypočíat popisné statistiky vzorku hodnot pixelů, které spadají do nějakých "zón" - polygonů
    - příklad: zjištění průměrných, minimálních a maximálních nadmořských výšek pro jednotlivá VZCHÚ
- vizualiace
  - plastický dojem - hillshade + nastylovaný DMT - průhlednost nebo míchání barev

### Wordclim / Bioclim
  - globální datová sada, 19 proměnných - teploty a srážky
  - využití v ekologii, biogeografii
  - symbologie
    - vymezení nejteplejších oblastí na Zemi
    - vymezení oblastí na Zemi s největším ročním úhrnem srážek


