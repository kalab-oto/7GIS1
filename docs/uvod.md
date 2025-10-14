# Úvod do QGIS 

## Data
- Ukázka geoportálu ČÚZK: [https://geoportal.cuzk.cz/](https://geoportal.cuzk.cz/) a stažení dat [RÚIAN](https://geoportal.cuzk.cz/(S(ty2lcmmvw3acbjehcphnhabj))/Default.aspx?mode=TextMeta&amp;side=dSady_RUIAN_vse&amp;text=dSady_RUIAN_vse&amp;head_tab=sekce-02-gp&amp;menu=331) (_Data RÚIAN ve formátu SHP - stát_)
- Popis formátu: [ESRI Shapefile](https://cs.wikipedia.org/wiki/Shapefile) - vícesouborový (multifile) formát pro vektorová data, nejvíce rozšířený. Vícesouborový znamená, že jsou data uložená ve více souborech, hlavně .dbf .shx .shp.

## QGIS - základní orientace

### Rozhraní
- Panely a lišty: zapínání/vypínání pomocí menu _View_, nebo pravým kliknutím na nějakou lištu
- Panely: _browser_ a _layer_
- Načtení dat: přes _browser_, nebo _drag and drop_ z průzkumníka
- Pohyb v mapovém okně: přiblížení
- Spodní lišta: souřadnice, měřítko, rendering (zapnutí/vypnutí vykreslování)
- Souřadnicový systém projektu (_CRS_): můžeme data zobrazit v jakémkoliv dostupném souřadnicovém systému
### Práce s daty
- Atributová tabulka: orientace v tabulce, popis okna
- Výběry: _selection_ - ruční výběr, a přiblížení na výběr
- Formuláře (_form_) a identifikace (_identify features_)
- Nástroj měření: orientační měření vzdáleností a ploch

### Projekt
- Uložení QGIS projektu, projekt má příponu .qgz, ukládá nastavení projektu, ale ne data

## Úkol k procvičení

- načtěte data obcí a ORP
- vyberte jakoukoliv obec
- zjistěte, v jakém ORP leží
- vyzkoušejte
  - konkrétní obce: Jistebník, Kyjovice, Tvrzice
  - různé způsoby dosažení tohoto cíle, např. bez využití identifikace

## Zdroje

- [https://gismentors.github.io/qgis-zacatecnik/intro/popis_rozhrani.html](https://training.gismentors.eu/qgis-zacatecnik/intro/popis_rozhrani.html)
- [https://docs.qgis.org/testing/en/docs/user_manual/introduction/qgis_gui.html](https://docs.qgis.org/testing/en/docs/user_manual/introduction/qgis_gui.html)