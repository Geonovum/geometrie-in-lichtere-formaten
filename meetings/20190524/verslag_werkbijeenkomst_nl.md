Werkbijeenkomst Geometrie in Lichtere Formaten

24 mei 2019, 10:00-12:00uur - Geonovum (Amersfoort)

| **Aanwezig: **                              | **Afgemeld: **                         |
|---------------------------------------------|----------------------------------------|
| John Schaap \| Kadaster                     | Paul van Genuchten \| geocat           |
| Willy Tadema \| Provincie Groningen         | Just van den Broecke \| Just Objects   |
| Han Welmer \| TNO-GDN                       | Dimitri van Hees \| Kadaster           |
| Wilko Quak \|KOOP                           | Maarten Hilferink \| Object Vision bv  |
| Daniël te Winkel \| Kadaster                | Pieter Bresters \| CBS                 |
| Wouter Visscher \| Kadaster                 |                                        |
| Erik van der Knaap \| gemeente Gooise Meren |                                        |
| Thijs Brentjens \| Geonovum                 |                                        |

Doel
====

Linda heet iedereen welkom en start met het doel van deze bijeenkomst: samen
kijken naar nieuwe geostandaarden zijnde lichtere alternatieve formaten voor
GML. GML is/was de standaard, maar er zijn nu ook alternatieve geo-standaarden.
Geonovum wil samen met het werkveld onderzoeken wat dit betekent voor
uitwisseling van geometrie en wat er aan extra documentatie en afspraken nodig
is om dit goed te kunnen toepassen. Resultaat van deze verkenning kunnnen zijn
best-practices, handreikingen, NL-profielen of bepaalde geo-standaarden richting
PTOLU (PasToeOfLegUit –lijst van standaarden van Forum Standaardisatie).

Terugblik vorige bijeenkomst
============================

Op 17 juli 2018 is ook een bijeenkomst geweest waarbij gekeken is naar andere
alternatieve formaten voor GML. De conclusies uit deze bijeenkomst waren:

-   GML is lastig en complex, met veel onnodige ballast. Daardoor GML-light
    varianten met ‘platgeslagen’ structuur

-   GeoJSON is te beperkt op gebied van o.m. 3D en CRS (WGS’84)

-   Weinig praktijkervaring met GeoPackage; technisch wel ondersteund.

-   Er zijn best practices nodig, met afspraken over o.m.

    -   objectnamen (schrijfwijze, nomenclatuur)

    -   Attribuutnamen

    -   attribuuttypen (ook spatial)

    -   attribuutlengtes’s

    -   Domeinwaarden

Sinds vorige bijeenkomst is het volgende gebeurd:

-   GeoPackage is aangemeld voor PTOLU
    (<https://www.geonovum.nl/over-geonovum/actueel/geopackage-aanmelden-voor-pas-toe-of-leg-uit-lijst>);
    GeoPackage is nu OGC standaard 

-   Aantal topics geopend op [GeoForum](https://geoforum.nl/).

Scope/discussie
===============

Scope/discussie voor deze werkbijeenkomst is de positionering van GML t.o.v.
andere formaten. John start de discussie met de opmerking dat er verschillende
manieren van data ophalen zijn,

1.  Vraag-antwoord: API’s: Ophalen van kleine aantallen of individuele objecten 

2.  Updaten van objecten middels mutaties (delta’s ofwel WAS/WORDT) 

3.  Bulk downloads van totaalstanden

Hier horen mogelijk andere formaten bij. Voor bulk downloads wordt nu GML vooral
toegepast maar dit is bewezen niet het meest handige formaat hiervoor.

Bij PDOK wordt nu veel uitgewisseld met GeoPackage, waarbij ook een schema mee
wordt uitgewisseld. GeoPackage leent zich verder voor raster tiling,
visualisatie, en metadata. Thijs merkt op dat ook voorbeeldvisualisatie
met GeoPackage kunnen worden meegeleverd.

Bij PDOK wordt GeoPackage toegepast voor kortere ETL-processen. PDOK werkt er
naar toe dat ook data-aanbieders gaan aanleveren in GeoPackage. PDOK kan er dan
direct een API opzetten.

TNO is al overgestapt naar aanlevering aan PDOK op GeoPackage. Deze overgang is
goed verlopen. Er wordt nagedacht over GeoJSON maar nog niet duidelijk is hoe
deze overdracht moet. Meervoudige geometrie en complexe datastructuren zijn een
hindernis.

Kracht van GeoPackage is dat er ook betekenisvolle attribuutnamen meegegeven
kunnen worden in tegenstelling tot beperkte maximale lengte van attribuutnamen
(10 karakters) in Shapefiles.

Thijs meldt dat Paul het voorstel heeft gedaan voor metadata in GeoPackage met
als doel metadata-afspraken op standaard manier opnemen in GeoPackage.
Internationaal standaardiseren van hele pakketje van GeoPackage is nodig.

Willy merkt op dat binnen provincies / overheid de uitwisselstandaard nu vooral
Shapefiles is waarbij bestanden veelal via email worden uitgewisseld.

Han merkt op dat Shapefile dichter zit bij databasemodellen, en niet bij de
informatiemodellen. Dit vraagt wel aan PDOK-kant om mappings te hebben. 

Nadeel van GeoPackage is dat het geen platte tekst, maar binair bestand is. Dit
is een risico in het kader van bestendigheid in toekomst.

Willy noemt het voorbeeld van onduidelijkheid over de draairichtingen van
polygonen: communicatie over draairichting in verschillende formaten is nodig.
Hoe zit dat in GeoJSON, PostGIS? Bij GeoJSON is het belangrijk om dit goed uit
te leggen omdat ook niet geo-mensen dit gebruiken. 

Veel techniek kan moeilijk overweg met meerdere geometrieën bij 1
feature. Kwaliteit van de geometrie is een issue, waarbij complexe geometrieën
in software vaak moet worden platgeslagen.

Verzoek is om voor GeoJSON een afspraak te maken dat coördinaten ook in RD mogen
en op 3 decimale posities wordt afgerond. Eenzelfde afspraak zou ook voor
afkappen coördinaten in WGS’84 moeten zijn om MB’s in uitwisseling te beperken.
WGS’84 is de standaard/default in GeoJSON, maar een onderlinge / Nederlandse
afspraak kan zijn dat ook andere CRS bijv. RD toegestaan is.

In URL-strategie kan opgelost worden dat ook andere CRS in GeoJSON toegepast kan
worden. De vraag is hoe om te gaan met transformatie en kwaliteit hiervan. John
merkt op dat het belangrijks is om onderscheid te maken tussen visualisatie en
toepassingen waarbinnen wel nauwkeurigheid nodig is. Afhankelijk van
schaalniveaus moet je een formaat kiezen.

In metadata bij bestand/data in formaat GML, GeoPackage of GeoJSON kan het
doel/toepassing van geometrie worden meegegeven, bijvoorbeeld ‘is geschikt voor
visualisatie’, of ‘is bedoeld voor meten en analyses’). 

GeoJSON wordt gebruikt buiten de GIS-wereld in gewone tekenpaketten.Provincie
Zuid-Holland redeneert: in API-strategie staat GeoJSON, dus ook ‘gewone’
ontwikkelaars aan de GeoJSON helpen. Ontwikkelaars pakken helaas nu ook andere
formaten.

KOOP publiceert wetten. Voorheen alleen teksten, maar nu teksten met data +
geometrie. GML is bestendig voor 50 jaar, wat een belangrijke eis is voor
KOOP. Gedachte is om GML-bestand de juridisch bindende data te laten bevatten,
maar de mogelijkheid te hebben voor een ‘makkelijk lezen’-knopje dat formaat
GeoPackage of GeoJSON uitlevert.

Focus is nu vooral op de situaties dat er altijd geometrie is. Maar hoe ga je om
met data zonder geometrie. Hoe past dat binnen GeoPackage en GeoJSON?
GeoPackage zit SQLLite onder, is dus niet een pure geo-techniek.

Erik vraagt of visualisatie als extensie op GeoPackage is gestandaardiseerd.
Styling is wel opgepakt door OGC Werkgroep en wordt mogelijk later opgepakt.

Daniel merkt op dat andere leverformaten in BRT gebruikersgroep zijn gepolst,
maar dan naast GML. GML wordt nu in veel bestaande processen gebruikt. BRT
achtergrondkaart wordt als GeoPackage aangeleverd als alternatief
voor FileGeodatabase. Er is een extra stap nodig om GeoPackage te genereren
uit FileGeodatabase.

Wilko: KOOP publiceert wetten. Voorheen alleen teksten, maar nu teksten met data
+ geometrie. GML is bestendig voor 50 jaar, belangrijke eis. GML
bestand juridisch bindende data. Mogelijkheden voor ‘makkelijk lezen’-knopje in
formaat GeoPackage / GeoJSON. 

PDF is authentieke bron, maar deze wordt omgezet naar andere (lichtere)
formaten. Er kunnen nu afspraken gemaakt worden over lengte van attribuutnamen.
Complexiteit van structuren. Aan de kant van bevoegd gezag wordt alles zo
simpel/plat mogelijk gehouden richting SFS0. Onderzocht wordt om
simpele GeoJSON in te laden in een web browser met mogelijkheid om te linken
naar juridisch bindende GML. Dus een frontend met simpelere versies wat vraagt
om een extra database er naast. Simpelere geometrie fungeert dan als soort van
index/portaal.

Gedachte bij PDOK is om meerdere endpoints toe te passen waar gebruikers
verschillende data uit andere API’s ophalen. Idee wordt geopperd voor een QGIS
plugin waarbij je vanuit kaartbeeld naar andere thema-bronnen kan linken. 

Thijs gebruikt sinds jaar al veel GeoPackage voor extracten en archiveren van
projecten/data, dus vooral lokaal. Als experiment heeft hij een GeoPackage
uitgeleverd aan partij die weinig tot geen geo-kennis heeft met een paar hints
voor tools. Dag later kreeg hij bericht dat het deze partij gelukt is om de
GeoPackage in te lezen. De toolset die Thijs toepast is veelal het zelfde: OGR –
QGIS. Thijs roept op om (verschillende) uitkomsten van verschillende ETL’s te
verzamelen.

GeoJSON zit vooal aan de API-kant en is makkelijk te lezen voor
niet-geogebruikers. Eenvoudiger handiger dan GML (makkelijkere taal).  Er moeten
ook gekeken worden naar toepassingen van GeoJSON met Linked Data ofwel
GeoJSON-LD. Linked Data kan worden toegepast voor metadatering over o.m.
toelichting/toepassing, definiteis en originele bron. Afspraken zijn nodig over
hoe je maken over hoe je linkt aan de authentieke / betrouwbare bron. 

Uit de discussie komt samengevat de volgende wensen/behoeften:

1.  Een handreiking om te weten voor welke toepassingsgebied je welke encoding
    toepast. Met daarin onderscheid tussen expert-gebruik vs. Visualisatie en de
    3 manieren van dataophalen (vraag-antwoord, mutaties en bulk download.

2.  Extra afspraken over toepassing van de volgende aspecten in GeoPackage en
    /of GeoJSON:

-   Metadata: originele bron, toepassing, nauwkeurigheid 

-   Default CRS voor GeoJSON + afronding aantal decimalen voor zowel WGS’84 en
    RD.

-   Visualisatie, extensies richting standaardisatie OGC) 

    1.  Pilot/demonstrator hoe een lichter formaat als index/portaal naar andere
        thema-bronnen ingezet kan worden? Voorbeelden zijn wetten/besluiten, of
        index/portaal voor ontsluiting thema’s (wegen, gebouwen).

1.  Een minimale set van voorbeeldbestanden als referentiedataset voor
    GeoPackage, GeoJSON (en GML).

Afspraken en vervolg
====================

Dus samenvattend:

-   Geonovum richt online werkomgeving in Github in voor verkenning naar
    Geometrie in lichtere formaten.

-   Geonovum stelt een referentiedataset samen en probeert dit te combineren met
    de WFS3-testweek.

-   Verzoek aan deelnemers om praktijkvoorbeelden en –ervaringen aan te dragen
    zowel technisch als praktijk. Dit kan via de Github of per email naar Linda
    of Arnoud.

-   Geonovum werkt de toepassingsgebieden, use cases, praktijkvoorbeelden en
    -ervaringen uit in een best-practice document. Streven is voor de zomer een
    eerste opzet te hebben die deelnemers kunnen aanvullen.
