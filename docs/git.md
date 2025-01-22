# Data
- AOPK - [MZCHÚ](https://data.nature.cz/ds/1) a [VZCHÚ](https://data.nature.cz/ds/3)
- [DIBAOD](https://www.dibavod.cz/index.php?id=27) - A03 - vodní tok (hrubé úseky)
- ČÚZK - [Data50](https://geoportal.cuzk.cz/(S(hbn3meceonqgld3dg4dk3mh3))/Default.aspx?mode=TextMeta&side=mapy_data50&metadataID=CZ-CUZK-DATA50-V&head_tab=sekce-02-gp&menu=22900)


# Prostorové dotazování - *Select by Location*

- funkce výběru, která vybere prvky v jedné vrstvě na základě zvolené prostorové interkace s prvky v druhé vrstvě - *"Vyber mi ty MZCHÚ které jsou součástí CHKO Beskydy"*


# Obalová zóna - *Buffer*

# Sloučení - *Dissolve*
- v češtině zatím předklad "Rozpustit"


# Překryvné operace - *Clip*, *Union*

## R

```r
# r code
library(terra)
x <- rast("asdyxc")
```

## Python
```py
# pyth code
import os
x = rast("asdyxc")
```

## Julia
```julia
s1 = "The quick brown fox jumps over the lazy dog α,β,γ"
println(s1)
```

## tabbed

??? example
    
    === "C"

        ``` c
        #include <stdio.h>

        int main(void) {
          printf("Hello world!\n");
          return 0;
        }
        ```

    === "C++"

        ``` c++
        #include <iostream>

        int main(void) {
          std::cout << "Hello world!" << std::endl;
          return 0;
        }
        ```


# Zdroje

- [GISMentors - QGIS začátečník - Prostorové analýzy](https://training.gismentors.eu/qgis-zacatecnik/vektorova_data/prostorove_analyzy.html)

- [GISMentors - QGIS začátečník - Atributové a prostorové dotazování](https://training.gismentors.eu/qgis-zacatecnik/vektorova_data/dotazovani.html)

- [QGIS Documentation - Vector menu](https://docs.qgis.org/3.34/en/docs/user_manual/introduction/qgis_gui.html#vector)

- [QGIS Documentation - Select by Location](https://docs.qgis.org/3.34/en/docs/user_manual/processing_algs/qgis/vectorselection.html#qgisselectbylocation) 
