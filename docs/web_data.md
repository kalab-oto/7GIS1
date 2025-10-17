# Prohlížecí a stahovací služby 

- prohlížecí a stahovací služby umožňují přístup k datům přes internet pomocí různých standardů
- k datům se přistupuje pomocí URL adresy služby, kterou poskytuje organizace spravující daná data
  
- příklad URL pro WMS službu ČÚZK - Ortofoto:
```
https://ags.cuzk.gov.cz/arcgis1/services/ORTOFOTO/MapServer/WMSServer?
```
- nejjednodušší a nejrychlejší způsob je přidat službu v panelu prohlížeče *Browser*. Na konci seznamu položek jsou příslušné položky pro WMS (*WMS/WMTS*), WFS (*WFS / OGC API - Features*) a ArcGIS Server (*ArcGIS REST Servers*).
    - nové připojení vytvoříme pravým kliknutím na položku a výběrem *New connection...* (*Nové připojení...*)
    - zadáme *Name* (název jak se bude dále zobrazovat v prohlížeči) a *URL* — url adresa připojení, kterou získáme od poskytovatele služby (AOPK, ČÚZK, atd.)
    - připojení stačí v seznamu rozkliknout a zobrazí se dostupné vrstvy, které lze přidat do projektu - přetažením myší nebo dvojklikem
    - vytvořené připojení zůstává v nastavení QGIS nezávsle na projektu a lze ho ihned používat po každém spuštění QGIS

- vrstvy v rámci služeb mohou být poskytované v různých souřadnicových systémech (CRS)
  - pokud je vrstva dostupná v souřadnicovém systému (CRS) projektu, QGIS si ze serveru vyžádá vrstvu v tomto CRS
  - v případě že QGIS vrstvu načte v jiném CRS, do CRS projektu se bude průběžně transformovat (tzv. *on-the-fly* transformace). Pro uživatele to znamená pouze možné zpomalení vykreslování vrstvy (např. u ortofot), protože se při každém vykreslení (posun, přiblížení) vrstva musí přepočítat.
- pokročilejší nastavení připojení lze provést v zprávci připojení, buď pomocí ikony *Open data source manager* (*Otevřít správce datových zdrojů*) v hlavním panelu nástrojů nebo v menu *Layer* (*Vrstva*). Zde je možné přidat připojení stejně jako v panelu, ale navíc zde lze nastavit i další parametry připojení (např. CRS)

## Typy služeb
- **WMS/WMTS** - Web Map Service/Web Map Tile Service
  - prohlížecí služba, slouží k zobrazení, ne práci s daty
  - služba ale může poskytovat informace na o souřadnicích/prvcích ('GetFeatureInfo'), v QGIS lze tuto funkci využít pomocí nástroje *Identify Features* (*Identifikovat Prvky*, ikona s písmenem i) 
  - k publikaci vektorových i rastrových dat, v GIS (klient) se zobrazí jako rastr
  
- **WFS** - Web Feature Service
  - služba pro práci s vektorovými daty
  - může sloužit po přímou práci s daty, ale je spíše vhodná například pro stahování dat při jejich pravidelné aktualizaci
  - v QGIS se data zobrazí jako vektorová vrstva, se kterou lze pracovat jako s běžnou vektorovou vrstvou

- **ArcGIS Server** 
  -  komplexní systém od firmy ESRI, může poskytovat různé služby včetně vlastních (ESRI)  *FeatureService* nebo *MapService*


## Příklady služeb
- ČÚZK
  - [Prohlížecí služby - WMS](https://geoportal.cuzk.cz/(S(u5gqffvhimhxstk12ficlzqd))/Default.aspx?mode=TextMeta&side=wms.verejne&text=WMS.verejne.uvod&head_tab=sekce-03-gp&menu=311)
      - Ortofoto, Archivní ortofoto, DMR 5G (digitální model reliéfu), DMP 1G (digitální model povrchu)
  - ČÚZK - [Prohlížecí služby - Esri ArcGIS Server](hhttps://geoportal.cuzk.cz/(S(0gg0vybvk3turge0wjun343s))/Default.aspx?mode=TextMeta&side=wms.AGS&text=WMS.AGS&head_tab=sekce-03-gp&menu=314)
      - Základní topografické mapy

- CENIA
  - [Dlaždicové služby - WMTS](https://geoportal.gov.cz/web/guest/wms)
      - Ortofoto 50. léta, II. vojenské mapování, III. vojenské mapování


- AOPK ČR
  - WFS — [https://portal23.nature.cz](https://portal23.nature.cz/publik_syst/ctihtmlpage.php?what=6103&X=X) nebo jednotlivě na [https://data.nature.cz](https://data.nature.cz)

- ČGS
  - [Webové služby](https://cgs.gov.cz/mapy-a-data/webove-sluzby) - WMS nebo ArcGIS Server
  - [Data](https://cgs.gov.cz/mapy-a-data/data) - různé přístupy, včetně souborů, WMS, ArcGIS Server i WFS

- Město Ostrava
    - [WMS](https://mapy.ostrava.cz/mapove-sluzby/wms/)
    - [Otevřená data](https://mapy.ostrava.cz/data/otevrena-data/opendata-info/)

## Úkol k procvičení
- přidejte do projektu 
  - WMS DMR 5G z ČÚZK
  - WFS vrstvu Velkoplošných zvláště chráněných území z datového portálu AOPK ČR
    - nastavte symbologii podle typu chráněného území
  - WMS Velkoplošných zvláště chráněných území z datového portálu AOPK ČR
    - vyzkoušejte identifikaci prvků na WMS vrstvách pomocí nástroje *Identify Features* (*Identifikovat Prvky*)

## Zdroje

- [https://gismentors.github.io/qgis-zacatecnik/webove_sluzby/index.html](https://gismentors.github.io/qgis-zacatecnik/webove_sluzby/index.html)
- [https://docs.qgis.org/3.44/en/docs/user_manual/managing_data_source/opening_data.html#connecting-to-web-services](https://docs.qgis.org/3.44/en/docs/user_manual/managing_data_source/opening_data.html#connecting-to-web-services)
