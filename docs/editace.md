# Tvorba nové vrstvy, editace geometrie a atributové tabulky
- ukázka WMS ortofoto 50.léta ([CENIA](https://www.cenia.cz/2022/02/17/historicka-ortofotomapa-z-50-let-se-otevira/))
- tvorba nové polygonové vrstvy (shapefile), lze nastavit souřadnicový systém, kódování textu, a vytvořit požadované sloupce/atributy (fields) - ty se dají vytvořit ale i samostatně později
- režim editace - přepíná se ikonkou tužky
- editace geometrie
	- tvorba polygonu
	- nástroj editace lomových bodů (vertexů, uzlů)
	- základní operace s geometrii polygonů (posun, rotace, škálování, rozdělení, sloučení)
	- přichytávání
		- nastavení
		- topologická editace
		- *Avoid overlap* zamezit protnutí
		- trasování s odsazením (*offset*)
- základní editace atributů
  - ruční zapisování hodnot
  - lze přidat nebo odebrat atributy (sloupce) pomocí tlačítek *New field* nebo *Delete field*, popř. pomocí funkce *Field calculator* - ikonka počítadla - (obsah následující hodiny)
	- hromadné zapisování pomocí panelu editace
		- zápis hodnot
			- čísla - 123
			- text - 'les'
			- sloupec - id (nebo "id")
		- možnost aktualizovat vše nebo jen prvky ve výběru
- problematika *multipart features* - multipolygony - jeden prvek (řádek v tabulce) může obsahovat více polygonů (např. CHKO Labské pískovce)

##### Zdroje
- [GISMentors - QGIS začátečník - Tvorba nových vrstev a jejich editace](https://training.gismentors.eu/qgis-zacatecnik/vektorova_data/editace.html)
- [QGIS Documentation - Creating layers](https://docs.qgis.org/3.34/en/docs/user_manual/managing_data_source/create_layers.html)
- [QGIS Documentation - Editing](https://docs.qgis.org/3.34/en/docs/user_manual/working_with_vector/editing_geometry_attributes.html)
