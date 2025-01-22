# Evropská a globální data a mapy

## NaturalEarthData
- stažení, Admin0, Graticules
- ukázka souřadnicových systémů 
  -  pro svět - Robinson, WGS84, Web Mercator
  -  konkrétní oblasti - UTM, S-JTSK, lokální systémy
     -  epsg.io
- tvorba mapy - ukázka funkcí Overviews, a Lock layers
- příklady:
  - Nový Zéland
  - Finsko
  - Island

## OpenStreetMap
  - globální datová sada, která vzniká ruční editací dat nebo importem, nekonzistentní ale snadno dostupná data
  - získání:
    - přes web - export oblasti - raw data
    - přes OverpassAPI - přímo v QGIS - plugin QuickOSM - key:value
      - příklady QuickOSM
        - kavárny v Ostravě
        - hospody v Ostravě
    - přes exportní služby - Geofabrik.de - připravená data, celé státy, regiony
      - příklady
        - Dánsko
        - Finsko
        - Island - mapa majáků
 
## Eurostat
- stažení tabulkových dat TSV (tab separated values)
- opakování práce s tabulkovými daty - načtení a připojení pomocí názvu země nebo kódu iso_a2