# Workshop Geometry in Lighter Formats

24 May 2019, 10 a.m. to 12 a.m. - Geonovum (Amersfoort)

| Present: | Not present: |

| --------------------------------------------- | ---
------------------------------------- |

| John Sheep \\ | Land Registry | Paul van Genuchten \\ | geocat |

| Willy Tadema \\ | Province of Groningen Just van den Broecke \\ | Just
Objects |

| Han Welmer \\ | TNO-GDN | Dimitri van Hees \\ | Land Registry |

| Wilko Quak \\ | BUY | Maarten Hilferink \\ | Object Vision bv |

| Daniël te Winkel \\ | Land Registry | Pieter Bresters \\ | CBS |

| Wouter Visscher \\ | Land Registry | |

| Erik van der Knaap \\ | municipality of Gooise Meren | |

| Thijs Brentjens \\ | Geonovum |

## Goal of the workshop

Linda welcomes everyone and starts with the goal of this meeting: together

look at new geo standards being lighter alternative formats for

GML. GML is / was the standard, but there are now alternative geo standards.

Geonovum wants to find out together with the professional field what this means
for

exchange of geometry and which additional documentation and agreements are
needed

to be able to apply these new standards properly. The result of this exploration
can be

best practices, guidelines, Dutch profiles or certain geo-standards on the
formal list of the Forum Standardization.

\#\# Looking back at the previous meeting

There was also a meeting on July 17, 2018 that looked at other alternative
formats for GML. The conclusions from this meeting were:

- GML is difficult and complex, with a lot of unnecessary ballast. Therefore
GML-light variants exist with "flattened" structure.

- GeoJSON is too limited in terms of 3D and CRS (WGS'84)

- Little practical experience with GeoPackage; technically supported.

- Best practices are needed, with agreements on, among other things.

    - object names (spelling, nomenclature)

    - Attribute names

    - attribute types (also spatial)

    - attribute lengths

    - Domain values

Since the last meeting, the following has happened:

- GeoPackage is registered for PTOLU

    (<https://www.geonovum.nl/over-geonovum/actueel/geopackage-aanregister-voor-pas-toe-of-leg-uit-lijst>); GeoPackage
is now OGC standard

- Number of topics opened on [GeoForum] (https://geoforum.nl/).

## Scope / discussion

Scope / discussion for this working meeting is the positioning of GML compared
to.

other formats. John starts the discussion with the comment that there are
several

ways of retrieving data:

1. Question-answer using APIs: retrieve small numbers or individual objects

2. Updating objects through mutations (deltas or WAS / BECOMES)

3. Bulk downloads of total datasets

This may include other formats. For bulk downloads, GML now mainly becomes

applied but this is proven not to be the most useful format for this.

At PDOK a lot is now exchanged with GeoPackage, which also includes a schema.

GeoPackage further lends itself to raster/grid tiling, visualization, and
metadata. Thijs also notes example visualizations can be included with
GeoPackage.

GeoPackage is used at PDOK for shorter ETL processes. PDOK asks data providers
to deliver in GeoPackage. PDOK is then able to set up an API immediately.

TNO has already switched to delivery to PDOK on GeoPackage. This transition went
well. GeoJSON is being considered, but it is not yet clear how this must be
done. Multiple geometry and complex data structures are one obstacle.

The strength of GeoPackage is that it can also contains meaningful attribute
names in contrast to limited maximum length of attribute names (10 characters)
in Shapefiles.

Thijs reports that Paul made the proposal for metadata in GeoPackage with
include metadata agreements as standard in GeoPackage. International
standardization of the entire GeoPackage package is required.

Willy notes that within the provinces / governments the exchange standard now
mainly is Shapefiles, where files are usually exchanged via email.

Han notes that Shapefile is closer to database models, and not to the conceptual
information models. This does require the PDOK side to have mappings.

The disadvantage of GeoPackage is that it is not plain text, but a binary file.
This is a risk in the context of future constancy.

Willy mentions the example of uncertainty about the directions of rotation of
polygons: communication about direction of rotation in different formats is
required. What about GeoJSON, PostGIS? At GeoJSON it is important to get this
right because even non-geo-people use this.

A lot of technology can hardly handle multiple geometries with 1 feature.
Quality of geometry is an issue where complex geometries in software often have
to be flattened.

The request is to make an agreement for GeoJSON that coordinates may also be in
Dutch CRS i.e. Rijksdriehoekstelsel (RD, EPSG:28992) and are rounded to 3
decimal places. The same agreement should also be for coordinate truncation in
WGS'84 to limit MBs in exchange. WGS'84 is the standard / default in GeoJSON,
but a mutual / Dutch agreement may be that other CRS, such as RD, is also
permitted.

In URL strategy it can be solved that other CRS can be applied in GeoJSON. The
question is how to deal with transformation and quality thereof. John notes that
it is important to distinguish between visualization and applications that
require accuracy. You have to choose a format depending on scale levels.

Metadata for data in format GML, GeoPackage or GeoJSON can include the
application of geometry, for example "is suitable for visualization", or "is
intended for measurement and analysis".

GeoJSON is used outside of the GIS world in normal drawing packages. The
province of South Holland argues: in API strategy, GeoJSON is included, so
"ordinary" developers also use GeoJSON. Unfortunately, developers are now also
taking other formats.

The focus is now on situations where there is always geometry. But how do you
handle data without geometry. How does that fit within GeoPackage and GeoJSON?
GeoPackage is under SQLLite, so is not a pure geo-technique.

Erik asks if visualization is standardized as an extension on GeoPackage.
Styling has been picked up by the OGC Working Group and may be picked up later.

Daniel notes that other delivery formats have been discussed in the BRT user
group, but in addition to GML. GML is now used in many existing processes. BRT
background map is supplied as GeoPackage as an alternative to FileGeodatabase.
An additional step is required to generate GeoPackage from FileGeodatabase.

Wilko: KOOP publishes laws. Previously only texts, but now texts with data +
geometry. GML is resistant for 50 years, which is an important requirement for
KOOP. The idea is to have the GML file contain the legally binding data, but
have the option of an "easy-to-read" button that delivers the GeoPackage or
GeoJSON format.

PDF is now the authentic source for laws, but this is converted to other
(lighter) formats. Agreements can now be made about the length of attribute
names. Complexity of structures. On the competent authority side, everything is
kept as simple / flat as possible towards SFS0. It is being investigated to load
simple GeoJSON into a web browser with the option of linking to legally binding
GML. So a front end with simpler versions which requires an extra database next
to it. Simpler geometry then acts as a type of index / portal.

The idea at PDOK is to apply multiple endpoints where users retrieve different
data from other APIs. Idea is suggested for a QGIS plugin where you can link
from map image to other theme sources.

Thijs has been using a lot of GeoPackage for years for extracting and archiving
projects / data, so mainly locally. As an experiment, he delivered a GeoPackage
to a party that has little to no geo-knowledge with a few hints for tools. The
next day he received a message that this party succeeded in reading the
GeoPackage. The toolset that Thijs applies is often the same: OGR - QGIS. Thijs
calls for the collection of (different) outcomes from different ETLs.

GeoJSON is mainly on the API side and is easy to read for non-geo users. Easier
more convenient than GML (easier language). GeoJSON applications with Linked
Data or GeoJSON-LD must also be considered. Linked Data can be used for metadata
about, among other things, explanation / application, definition and original
source. Agreements are needed about how you make about how you link to the
authentic / reliable source.

GML is now very suitable for dedicated validation. The question is whether or
how this applies to other formats.

In summary, the following wishes / needs emerge from the discussion:

1. A guide to know for which application area you apply which encoding. With a
distinction between expert use vs. Visualization, and distinction between the 3
ways of data retrieval (question-answer, mutations and bulk download).

2. Additional agreements on the application of the following aspects in
GeoPackage and / or GeoJSON:

• Metadata: original source, application, accuracy

• Default CRS for GeoJSON + rounding of decimal places for both WGS'84 and RD.

• Visualization, extensions towards standardization OGC)

3. Pilot / demonstrator how a lighter format can be used as an index / portal to
other theme sources. Examples are laws / decisions, or an index / portal for
opening up themes (roads, buildings).

4. A minimal set of sample files as a reference data set for GeoPackage, GeoJSON
(and GML).

## Follow-up

So in summary:

• Geonovum sets up an online working environment in Github to explore Geometry
in lighter formats.

• Geonovum puts together a reference data set and tries to combine this with the
WFS3 test week.

• Request to participants to provide practical examples and experiences, both
technical and practical. This can be done via the Github or by email to Linda or
Arnoud.

• Geonovum elaborates the application areas, use cases, practical examples and
experiences in a best-practice document. The aim is to have a first set-up
before the summer that participants can supplement.

Geonovum will organize a follow-up meeting after the summer.
