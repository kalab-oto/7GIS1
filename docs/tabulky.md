# 5. Práce s tabulkovými daty - souřadnice bodů, propojení dat
#### data:
- přiložené tabulky
  - `stromy_wgs.csv` - fiktivní cvičná datová sada
  - `ndop_lepidoptera.csv` - předzpracovaná datová sada získaná z NDOP - [Nálezová databáze AOPK](https://portal.nature.cz/nd/)   - pro vyhledávání a stažení dat je nutná registrace, potom je možné stáhnout data na webové stránce mebo přímo v QGIS pomocí zasuvného modulu NDOP Downloader
  - `csu_DEM01.csv` - předzpracovaná datová sada získanáz ČSU - [Veřejná databáze - Český statistický úřad](https://vdb.czso.cz/vdbvo2/faces/cs/index.jsf?page=statistiky&katalog=33155#katalog=33156)
- ČÚZK ([RUIAN](https://geoportal.cuzk.cz/(S(0c4pelr2yzdzis33tse4fyxn))/Default.aspx?lng=CZ&mode=TextMeta&side=dsady_RUIAN_vse&metadataID=CZ-00025712-CUZK_SERIES-MD_RUIAN-STATY-SHP)) kraje (`VUSC_P.shp`)


#### obsah hodiny:
- popis formátu `.csv`
- tabulková data se souřadnicemi XY - zobrazení souřadnic v tabulce jako body v QGIS
    - načtení dat s odděleným textem *Add Delimited Text Layer*
    - zobrazili jsme soubor jako bodovou vrstvu
    - problematika chybného nastavení souřadnicového systému dat
        - nastavení souřadnicového systému (CRS) pokud se nahrává vrstva a nerozpozná se CRS
	- fiktivní data ve WGS84 (EPSG:4326) - `stromy_wgs.csv`
		- načtení dat s nastavení chybného CRS a následná oprava
	- data NDOP - motýly CHKO Poodří a CHKO Beskydy S-JTSK (EPSG:5514) - `lepidoptera_besk_pood.csv`
		- volitelné stylování
		- vysvětlení zdroje dat NDOP
- připojení tabulky k atributové tabulce polygonové vrstvy (data ČSÚ- počty obyvatel, a data ČÚZK - RUIAN -kraje) - `csu_DEM01.csv`
	- popis datového zdroje ČSÚ
	- práce s předpřipravenou tabulkou (originál lze získat zde: https://vdb.czso.cz/vdbvo2/faces/cs/index.jsf?page=statistiky&katalog=33155#katalog=33156)
	- připojení předzpracované tabulky ČSÚ k tabulce polygonů krajů na základě společného klíče (identifikátoru) v našem případě název kraje
		- volitelné stylování
		- seznámení se s s typem dat (long vs. wide data) a s principem tvorby kartogramu (relativní hodnoty)

##### zásuvné moduly - Plugins
- ve zbytku hodiny jsme si ukázali princip, instalaci a použití zásuvných modulů - pluginů v QGIS
  - instalace v menu *Plugins -> Manage and Install Plugins ...*

#### zdroje:
tabulky:

- [GISMentors - QGIS začátečník - Import XY dat](https://training.gismentors.eu/qgis-zacatecnik/vektorova_data/import_delim.html)
- [GISMentors - QGIS začátečník - Připojení tabulky](https://training.gismentors.eu/qgis-zacatecnik/vektorova_data/join.html)
- [QGIS Documentation - Importing a delimited text file](https://docs.qgis.org/3.34/en/docs/user_manual/managing_data_source/opening_data.html#importing-a-delimited-text-file)

pluginy:

- [GISMentors - QGIS začátečník - QGIS Pluginy](https://training.gismentors.eu/qgis-zacatecnik/2.14/ruzne/qgis_pluginy.html#)
- [QGIS Documentation - QGIS Plugins](https://docs.qgis.org/3.34/en/docs/user_manual/plugins/plugins.html#qgis-plugins)
