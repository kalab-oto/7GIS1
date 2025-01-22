# Analýza vektorových dat - prostorový výběr - překryvné operace

## Data
- AOPK - [MZCHÚ](https://data.nature.cz/ds/1) a [VZCHÚ](https://data.nature.cz/ds/3)
- [DIBAOD](https://www.dibavod.cz/index.php?id=27) - A03 - vodní tok (hrubé úseky)
- ČÚZK - [Data50](https://geoportal.cuzk.cz/(S(hbn3meceonqgld3dg4dk3mh3))/Default.aspx?mode=TextMeta&side=mapy_data50&metadataID=CZ-CUZK-DATA50-V&head_tab=sekce-02-gp&menu=22900)

## Vybrané analýzy
-  všechny vybrané analýzy jsou dostupné v menu *Vektor -> Geoprocessing tools*
-  lze spustit na všechny prvky ve vrstvě, nebo jen na ty vybrané


### Prostorové dotazování - *Select by Location*
- funkce výběru, která vybere prvky v jedné vrstvě na základě zvolené prostorové interkace s prvky v druhé vrstvě - *"Vyber mi ty MZCHÚ které jsou součástí CHKO Beskydy"*
- najdeme i v liště nástrojů - *Select by Location*

### Obalová zóna - *Buffer*
- analýza, pomocí které lze vytvořit novou polygonovu vrstvu s hranicí v určité vzdálenosti od stávajících prvků
- použití např. při definování ochranných pásem, nebo výpočtu vzdáleností pro další analýzy (např. kolik bodů je v okruhu 100 metrů od dálnice)
- můžeme zvolit parametr *Dissolve* ("Rozpustit")- sloučení prvků do jednoho, pokud se dotýkají. Vznikne tak 1 multipolygon místo několika jednotlivých polygonů, lze spustit i dodatečně
  
### Sloučení - *Dissolve*
- v češtině zatím předklad "Rozpustit"
- sloučí prvky ve vrstvě
- buď všechny, nebo na základě zvoleného atributu (např. všechny dálnice do jednoho prvku)
- ztratíme informaci z původní atributové tabulky, zůstane pouze první prvek

### Překryvné operace - *Clip*, *Union*
- analýza, která vytvoří novou vrstvu prvků na základě průniku dvou vrstev, týká se tak jak geometrie prvků, tak jejich atributů
- *Clip* - ořezání - výsledkem je vrstva, která obsahuje pouze průnik obou vrstev s atributy jen vstupní vrstvy
- *Union* - sjednocení  - výsledkem je vrstva, která obsahuje průnik obou vrstev i s částmi které se neprotínají, atributy obou vrstev jsou zachované
- domácí úkol: zkuste další časté překryvné operace jsou *Intersection* a *Difference*
    - *Intersect* - průnik - výsledkem je vrstva, která obsahuje pouze průnik obou vrstev s atributy obou vrstev
    - *Difference* - rozdíl - výsledkem je vrstva, která obsahuje prvky z první vrstvy, které se neprotínají s druhou vrstvou

## Zdroje

- [GISMentors - QGIS začátečník - Prostorové analýzy](https://training.gismentors.eu/qgis-zacatecnik/vektorova_data/prostorove_analyzy.html)

- [GISMentors - QGIS začátečník - Atributové a prostorové dotazování](https://training.gismentors.eu/qgis-zacatecnik/vektorova_data/dotazovani.html)

- [QGIS Documentation - Vector menu](https://docs.qgis.org/3.34/en/docs/user_manual/introduction/qgis_gui.html#vector)

- [QGIS Documentation - Select by Location](https://docs.qgis.org/3.34/en/docs/user_manual/processing_algs/qgis/vectorselection.html#qgisselectbylocation) 
