# README

## Konvertierung von xlsx nach csv

Import from UTF-8, Language German, Comma separated, Text delimiter ", Quoted
field as text:

IMPORTANT! : --convert-to converts only the first sheet!!!

```shell
libreoffice --headless --unaccept=accept-string --convert-to csv:"Text - txt - csv (StarCalc)":44,34,76,1,,1031,true,true Kindergruppen_Daten\ Website_05-2017.xlsx
```

- 44 the comma
- 34 the double quote character ASCII value.
- 76 is the number of the UTF-8 encoding
- For details of the filter options see: <https://wiki.openoffice.org/wiki/Documentation/DevGuide/Spreadsheets/Filter_Options#Filter_Options_for_the_CSV_Filter>

## Alternative 
https://github.com/dilshod/xlsx2csv

## Geocodierung

```shell
HEREAPPID=XXXXXXXXXXXXXXXXXXXX HEREAPPCODE=XXXXXXXXXXXXXXXXXXXXXX /opt/geocodify/geocodify.js --source=here --addressfields ["NABU Stadtverband"] Kindergruppen_Daten\ Website_05-2017.csv > Kindergruppen_Daten\ Website_05-2017-geocodify.csv
```

## Umwandeln nach GeoJSON

```shell
ogr2ogr -f "GeoJSON" kindergruppen.geojson Kindergruppen_Daten\ Website_05-2017-geocodify.csv -oo X_POSSIBLE_NAMES=lon -oo Y_POSSIBLE_NAMES=lat -oo KEEP_GEOM_COLUMNS=NO
```

## Storchenkoffer

libreoffice --headless --unaccept=accept-string --convert-to csv:"Text - txt - csv (StarCalc)":44,34,76,1,,1031,true,true Storchenkoffer_Ausleihstationen.xlsx 

HEREAPPID=TG4UcWVKDpwsnVYeTN1P HEREAPPCODE=6kTLfjLDay5H2epKE0oSbw /opt/geocodify/geocodify.js --source=here --addressfields [Straße Postleitzahl Ort] Storchenkoffer_Ausleihstationen.csv > Storchenkoffer_Ausleihstationen-geocodify.csv

## Daten 

- Öffne »NAJU.de«: https://cloud.naju.de/index.php/s/HeAYwXkpz8skNnj
- https://cloud.naju.de/index.php/s/HeAYwXkpz8skNnj/download
- https://cloud.naju.de/index.php/s/HeAYwXkpz8skNnj/download?path=%2FNAJU_Gruppen_aktualisieren&files=Kindergruppen_Daten%20Website_05-2017.xlsx&downloadStartSecret=ldpuu0flwmj
- https://cloud.naju.de/index.php/s/HeAYwXkpz8skNnj/download?path=%2FNAJU_Termine_aktualisieren&files=NAJU.de_Termine.xlsx&downloadStartSecret=hmas3anapdh

