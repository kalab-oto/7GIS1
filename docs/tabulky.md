# Tabulková data

## data:
- `ndop_rys_vlk.csv` - data exportovaná z NDOP - [Nálezová databáze AOPK](https://portal.nature.cz/nd/)- pro vyhledávání a stažení dat je nutná registrace, potom je možné stáhnout data na webové stránce mebo přímo v QGIS pomocí zasuvného modulu NDOP Downloader
- `observations-638235.csv`  - data exportovaná z iNaturalist - [iNaturalist.org](https://www.inaturalist.org/) - pro vyhledávání a stažení dat je nutná registrace, potom je možná stáhnout data přímo z webové stránky v možnostech filtrování výskytů

- `csu_DEM01.csv` - předzpracovaná datová sada získanáz ČSU - [Veřejná databáze - Český statistický úřad](https://vdb.czso.cz/vdbvo2/faces/cs/index.jsf?page=statistiky&katalog=33155#katalog=33156)
- ČÚZK ([RUIAN](https://geoportal.cuzk.cz/(S(0c4pelr2yzdzis33tse4fyxn))/Default.aspx?lng=CZ&mode=TextMeta&side=dsady_RUIAN_vse&metadataID=CZ-00025712-CUZK_SERIES-MD_RUIAN-STATY-SHP)) kraje (`VUSC_P.shp`)

 
## Formát `.csv` (Comma Separated Values)
- primitivní textový formát pro tabulková data, kde jednotlivé hodnoty jsou odděleny čárkou, ale častý je i jiný oddělovač, např. středník nebo tabulátor
- neobsahuje žádné formátování, pouze čistá data v textovém souboru, je tedy jednodušše strojově čitelný
- tabulkové procesory (Excel, Calc) slouží pro zpracování a vizualizaci dat, kdy používají vlastní formáty (`.xlsx`, `.ods`,...), tyto programy zpravidla umožňují export i import z `.csv` formátu, který je vhodnější pro výměnu dat
- při načítání je nutrné správně nastavit oddělovač, kódování znaků (UTF-8, Windows-1250,...) a případně další parametry (desetinná čárka/tečka, hlavička tabulky,...), to platí pro všechny programy

## Tabulková data s geometrií (XY)
- vysvětlení zdroje dat NDOP a iNaturalist
- geometrie může být zapsanáa v tabulce různými způsoby, nejčastěji jako souřadnice bodů - X a Y (nebo zeměpisná šířka a délka), ale existuje i zápis pro ostatní typy  geometrie (linie, polygony) např. ve formátu [WKT (Well-Known Text)](https://en.wikipedia.org/wiki/Well-known_text_representation_of_geometry)
- zobrazení souřadnic v tabulce jako body v QGIS
    - načtení dat s odděleným textem *Add Delimited Text Layer*
	- data NDOP - zveřejněná data výskytu vlka a rysa (EPSG:5514) - `ndop_rys_vlk.csv`
	- inaturalist data ve WGS84 (EPSG:4326) - `observations-638235.csv`
    - problematika chybného nastavení souřadnicového systému dat
		- načtení dat s nastavení chybného CRS a následná oprava ve vlastnostech vrstvy
		


## Připojení tabulky k existujícím prostorovým datům
- popis datového zdroje ČSÚ
- práce s předpřipravenou tabulkou
- připojení předzpracované tabulky ČSÚ k tabulce polygonů krajů na základě společného klíče (identifikátoru) v našem případě název kraje

- RUIAN kraje - `csu_DEM01.csv`
	- seznámení se s s typem dat (long vs. wide data) a s principem tvorby kartogramu (relativní hodnoty)

<!-- ## zásuvné moduly - Plugins
- ve zbytku hodiny jsme si ukázali princip, instalaci a použití zásuvných modulů - pluginů v QGIS
  - instalace v menu *Plugins -> Manage and Install Plugins ...*
  - group stats ? -->

## Úkol k procvičení
- načtěte data - `ndop_lepidoptera.csv` - předzpracovaná datová sada získaná z NDOP - [Nálezová databáze AOPK](https://portal.nature.cz/nd/) 
- nastylujte body podle druhu, přidejte popisky s českým názvem druhu
- zjistěte kolik je záznamů v CHKO Poodří a kolik v CHKO Beskydy

## zdroje:
tabulky:

- [GISMentors - QGIS začátečník - Import XY dat](https://gismentors.github.io/qgis-zacatecnik/vektorova_data/import_delim.html)
- [GISMentors - QGIS začátečník - Připojení tabulky](https://gismentors.github.io/qgis-zacatecnik/vektorova_data/join.html)
- [QGIS Documentation - Importing a delimited text file](https://docs.qgis.org/3.44/en/docs/user_manual/managing_data_source/opening_data.html#importing-a-delimited-text-file)

<!-- pluginy:

- [GISMentors - QGIS začátečník - QGIS Pluginy](https://gismentors.github.io/qgis-zacatecnik/2.14/ruzne/qgis_pluginy.html#)
- [QGIS Documentation - QGIS Plugins](https://docs.qgis.org/3.44/en/docs/user_manual/plugins/plugins.html#qgis-plugins) -->
