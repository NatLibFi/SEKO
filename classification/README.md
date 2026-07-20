# Classfication
## Hornbostel-Sachs
The original German version of the classification was translated into Finnish and published by Leisiö in 1974.
- Curt Sachs ja Erich M. von Hornbostel: "Luonnollisten soitinten luokitusjärjestelmä"
- Translated by **Timo Leisiö** and published in the journal "Musiikki no. 1-4, 1974".  [Library record](https://api.finna.fi/v1/record?id=gmc.4104&lng=fi&prettyPrint=1)
- The base for translation was the orignal article “Systematik der Musikinstrumente. Ein Versuch.” Zeitschrift für Ethnologie, 4 ja 5: Jahrgang 1914, pages 553-590.

## Availability
### Finnish versions
- The 1974 translation was available online as a PDF by the University of Tampere, but it has been removed, and not archived by the wayback machine:
 `http://www.uta.fi/laitokset/mustut/soitinluokitus.pdf` 
 - A revised version was published in 2010. Leisiö, T. (2010). Luonnollisten soitinten luokitusjärjestelmä. Toinen, uudistettu laitos. Musiikintutkimuksen laitos. https://www.yumpu.com/fi/document/view/5067218/luonnollisten-soitinten-luokitusjarjestelma-pdf/ (Retrieved 2026-07-18)
  - Since then a new updated version of the classification was published by the MIMO network of Music Libraries, especially adding the electronic instruments as a new category.
  - MIMO has now 50+ sublcasses of [5 Electrophones](http://www.mimo-db.eu/HornbostelAndSachs/6154)

### MIMO versions
- MIMO was not retrievable from the API, but it has been available in JSON format in the Github repository [Hornbostel-Sachs Classifications and Musical Instruments Translation Database (JSON)](https://github.com/modavis-project/musical-instrument-classes) of the [MODAVIS-project](https://modavis.org/) by by Dominik Ukolov in Germany.
- [Revision of the Hornbostel-Sachs Classification of Musical Instruments by the MIMO Consortium](https://mimo-international.com/documents/Hornbostel%20Sachs.pdf) MIMO publication with sources, published 8 July 2011, 26 pages, format:PDF (Retrieved 2026-07-20)

- 
### Other sites
- https://web.archive.org/web/20090616132940/http:/www.wesleyan.edu/vim/svh.html


## SEKO with classification
Consider including Hornbostel-Sachs classification as a separate scheme in seko:

Best option would seem to create a new translation in Finnish based on the MIMO version of the classification. 
Basic terminology would be the same as with Leisiö, but many of the descriptions have been expanded and there was an effor to decrease of the 1914 German cultural skewness. (e.g. removing "eskimoes and negroes".

Another option would be label the groups as "Instrument families" with the more general termonology used by MIMO Cllections
[instrument families](https://mimo-international.com/MIMO/instrument-families.aspx) - these are in principla the H-S classes but without the notations.
- Wind instruments
- Percussion instruments
- Stringed instruments
- Elements of musical instruments
- Keyboard instruments
- Mechanical instruments
- Other instruments
- Mirlitons
- Electronic instruments

### Preliminary activities and preparation
- Both the Leisiö 2010 and Hornbostel Sachs 2011 data (via MODAVIS) have been loaded into a single OpenRefine dataset for further comparisons and possibly a new Finnish translation.
- Wikidata mapping would be a nice addtion perhaps through reconciliation if an appropreate way to tease it out from the SPARQL endpoint. Manual mapping possible but tedious.
- Making this available is under consideration.
  - The MODAVIS datased had CC0 license and
  - Leisiö 3020 dataset is available as a PDF, The TU Reseasrchportal entry says **Licence: Unspecified** [Luonnollisten soitinten luokitusjärjestelmä. Toinen, uudistettu laitos](https://researchportal.tuni.fi/en/publications/luonnollisten-soitinten-luokitusj%C3%A4rjestelm%C3%A4-toinen-uudistettu-lai/) - there is no mention in the document.


## Schema, namespace, notatione and identifiers
The scheme could be used by SEKO3 either 
- as the main hierarchy or
- as a separate alternative hierarchy/grouping in the same way YSO is using "[numeric groups](https://finto.fi/yso/en/groups?clang=fi)"
  - This can be created with skos-isothes: and isothes:ConceptGroup elements which can use hierarchy properties isothes:superGroup/isothes:hasSubGroup and then include the skos:Conecept elemnts with skos:member property.

## Data
- MIMO uses  `@prefix hornbostelandsachs: <http://www.mimo-db.eu/HornbostelAndSachs/> .`
- Each item has   `skos:inScheme <http://www.mimo-db.eu/HornbostelAndSachs#> ;`
- Mapping to MIMO with `skos:exactMatch`  https://vocabulary.mimo-international.com/HornbostelAndSachs/en/
- The notation would be the same in both
- An identifier model needs to configured - same as in MIMO COllections


## Research
- Citation:  Lee, D. (2019). Hornbostel-Sachs Classification of Musical Instruments. Knowledge Organization, 47(1), pp. 72-91.
   - doi: 10.5771/0943-7444-2020-1-72
   - https://www.imrpress.com/journal/KO/47/1/10.5771/0943-7444-2020-1-72
   - https://openaccess.city.ac.uk/id/eprint/22554/1/IEKO%2520Hornbostel-Sachs%2520VERSION%2520FOR%2520KO%2520post%2520minor%2520revision.pdf
