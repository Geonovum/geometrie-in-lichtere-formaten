## Ervaringen met GeoPackage en GeoJSON tijdens de WFS 3 werkweek

Ontwikkelaars van PDOK hebben tijdens de [Geonovum/PDOK WFS 3 werkweek](https://www.geonovum.nl/over-geonovum/actueel/de-ins-en-outs-van-wfs3-6-juni-2019) ervaringen opgedaan met zowel GeoPackage als GeoJSON. Hieronder een kort verslag: 

### GeoPackage
GeoPackage is gebruikt als bestandsformaat in combinatie met WFS 3.0 (OGC API: Features). Tijdens het experiment is er gewerkt met BGT data. 

- Bestanden worden soms erg groot, bijvoorbeeld de landelijke set van BGT wegdelen was meer dan 60gb. 
- GeoPackage werkt doorgaans met platte datastructuren, de vaak complexe modellen van basisregistraties moeten dus worden 'platgeslagen'. 
- GeoPackage werkt standaard met numerieke ID's. Dit geeft problemen met ID's van basisregistraties, die niet altijd numeriek zijn. De applicatie is aangepast om GeoPackage bestanden te kunnen doorzoeken op basis van het lokaal ID van basisregistraties in plaats van het standaard, numerieke ID. 

### GeoJSON
Tijdens de WFS 3 werkweek is er een applicatie met GeoJSON gebouwd in GO, omzetting WKB naar WKT.

- Een prima formaat voor de meeste toepassingen. 
- Een voordeel van dit formaat is dat het te lezen is in een tekst ditor, in tegenstelling tot GeoPackage bestanden die binair zijn. Dit maakt GeoJSON wat eenvoudiger in gebruik. 
- GeoJSON schrijft WGS 84 voor; dit maakt het geschikt voor visualisatie op het web.
- WFS 3 kan in combinatie met GML worden gebruikt, dit is alleen nog interessant als er behoefte is aan nauwkeurigere geometrieën of aan arcs (die in GeoJSON niet worden ondersteund). Andere use cases voor GML/XML zien de PDOK ontwikkelaars niet meer.
- In veel gevallen is de nauwkeurigheid van GeoJSON voldoende; op het [Geoforum](https://geoforum.nl) wordt er zelden naar gevraagd. Belangrijker is vindbaarheid van data. De aanbeveling is om GeoJSON alleen in combinatie met WGS 84 te gebruiken. 

### Algemeen 
- WFS 2.0 blijft ook bestaan, naast WFS 3.0 en GML extracten. 
- Het is belangrijk om richting houders van de registraties te melden dat voor WFS 3/GeoJSON laagdrempelige ontsluiting de nauwkeurigheid van de brondata wordt verlaagd.  Via NGR metadata kan nauwkeurigheid hoog/laag worden gecommuniceerd. 
- WFS 3 was eenvoudig in web viewer en QGIS in te laden. 
- Metadata: WFS 3 / OGC API: Features komt nu niet voor in het Nederlandse metadata profiel, en valt dus nu onder 'other'. Metadata profiel moet worden uitgebreid.
- Afnemers moeten gaan wennen aan afnemen vanuit meerdere endpoints. Een idee is om een platgeslagen, envoudig kaartje als index/portaal naar complexere data endpoints te laten fungeren.
