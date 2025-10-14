# Webové služby a zdroje dat

- souřadnicové systémy a transformace (CRS)

Webové služby (WMS, WFS, ArcGIS Server)

- nejjednodušší a nejrychlejší způsob je přidat službu v panelu prohlížeče *Browser*. Na konci seznamu položek jsou příslušné položky pro WMS (*WMS/WMTS*), WFS (*WFS / OGC API - Features*) a ArcGIS Server (*ArcGIS REST Servers*).
    - vytvoříme nové připojení pravým kliknutím na položku a výběrem *New connection...*
    - zadáme *Name* (název jak se bude zobrazovat v panelu) a *URL* — url adresa připojení, kterou získáme od poskytovatele služby (AOPK, ČÚZK, atd.)
    - vytvořené připojení zůstává v instalaci QGIS pro všechny projekty

- Prohlížecí služby:

    - ČÚZK - [Prohlížecí služby - WMS](https://geoportal.cuzk.cz/(S(u5gqffvhimhxstk12ficlzqd))/Default.aspx?mode=TextMeta&side=wms.verejne&text=WMS.verejne.uvod&head_tab=sekce-03-gp&menu=311)
    - dmr a dmp
    - CENIA - https://geoportal.gov.cz/web/guest/wms

- Stahovací služby:
    - AOPK - WFS — https://portal23.nature.cz/publik_syst/ctihtmlpage.php?what=6103&X=X nebo jednotlivě na https://data.nature.cz
    - ČGS - https://cgs.gov.cz/mapy-a-data/data (obsahuje i WMS)

Další zdroje dat — WMS i ke stažení:


- Kraje a obce mohou poskytovat prostorová data — [Ostrava](https://mapy.ostrava.cz/data/otevrena-data/opendata-info/)


Zdroje:

- https://gismentors.github.io/qgis-zacatecnik/webove_sluzby/index.html
- https://docs.qgis.org/3.44/en/docs/user_manual/managing_data_source/opening_data.html#connecting-to-web-services
