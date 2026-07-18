# Classfication
## Hornbostel-Sachs
The original German version of the classification was translated into Finnish and published by Leisiö in 1974.
- Curt Sachs ja Erich M. von Hornbostel: "Luonnollisten soitinten luokitusjärjestelmä"
- Translated by **Timo Leisiö** and published in the journal "Musiikki no. 1-4, 1974".  [Library record](https://api.finna.fi/v1/record?id=gmc.4104&lng=fi&prettyPrint=1)
- The base for translation was the orignal article “Systematik der Musikinstrumente. Ein Versuch.” Zeitschrift für Ethnologie, 4 ja 5: Jahrgang 1914, pages 553-590.
## Availability
- The 1974 translation was available online as a PDF by the University of Tampere, but it has been removed, and not archived by the wayback machine:
 `http://www.uta.fi/laitokset/mustut/soitinluokitus.pdf` 
 - A revised version was published in 2010. Leisiö, T. (2010). Luonnollisten soitinten luokitusjärjestelmä. Toinen, uudistettu laitos. Musiikintutkimuksen laitos. https://www.yumpu.com/fi/document/view/5067218/luonnollisten-soitinten-luokitusjarjestelma-pdf/ (Retrieved 2026-07-18)
 
Since then a new updated version of the classification was published by the MIMO network of Music Libraries, especially adding the electroinic instruments as a new category.


Consider including Hornbostel-Sachs classification as a separate scheme in seko:

Best option would seem to create a new translation based on the MIMO version of the classification. 
Basic terminology would be the same as with Leisiö, but many of the descriptions have been expanded.

## Schema, namespace, notatione and identifiers
The scheme could be used by SEKO3 either 
- as the main hierarchy or
- as a separate alternative hierarchy/grouping in the same way YSO is using "[numeric groups](https://finto.fi/yso/en/groups?clang=fi)"
  - This can be created with skos-isothes: and isothes:ConceptGroup elements which can use hierarchy properties isothes:superGroup/isothes:hasSubGroup and then include the skos:Conecept elemnts with skos:member property.

Data
- MIMO uses  `@prefix hornbostelandsachs: <http://www.mimo-db.eu/HornbostelAndSachs/> .`
- Each item has   `skos:inScheme <http://www.mimo-db.eu/HornbostelAndSachs#> ;`
- Mapping to MIMO with `skos:exactMatch`  https://vocabulary.mimo-international.com/HornbostelAndSachs/en/
- The notation would be the same in both
- An identifier model needs to configured - same as in MIMO?


