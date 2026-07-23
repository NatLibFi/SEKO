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
- Both the Leisiö 2010 and Hornbostel Sachs 2011 data (via MODAVIS) have been loaded into a single OpenRefine dataset for further comparisons and possibly a new Finnish translation. The loaded dataset has the MIMO ID values which, with the hornbostelsachs: namespace, would be the mappings to MIMO.
- Wikidata mapping would be a nice addtion perhaps through reconciliation if an appropreate way to tease it out from the SPARQL endpoint. Manual mapping possible but tedious. MIMO vocabulary has mappings to dbpedia but a wikidata record should have the dbpedia- link, too.
- Making this available is under consideration.
  - The MODAVIS datased had CC0 license and
  - Leisiö 3020 dataset is available as a PDF, The TU Reseasrchportal entry says **Licence: Unspecified** [Luonnollisten soitinten luokitusjärjestelmä. Toinen, uudistettu laitos](https://researchportal.tuni.fi/en/publications/luonnollisten-soitinten-luokitusj%C3%A4rjestelm%C3%A4-toinen-uudistettu-lai/) - there is no mention in the document.


## Schema, namespace, notation and identifiers
The scheme could be used by SEKO3 either 
- as the main hierarchy or
- as a separate alternative hierarchy/grouping in the same way YSO is using "[numeric groups](https://finto.fi/yso/en/groups?clang=fi)"
  - This can be created with skos-thes: and isothes:ConceptGroup elements which can use hierarchy properties isothes:superGroup/isothes:hasSubGroup and then include the skos:Conecept elemnts with skos:member property.



## Data
Will need to consult with Finto-team concerning the application on the Finto Skosmos server.

- MIMO uses  `@prefix hornbostelandsachs: <http://www.mimo-db.eu/HornbostelAndSachs/> .`
- Each item has   `skos:inScheme <http://www.mimo-db.eu/HornbostelAndSachs#> ;`
- The notation would be the same in both

### Class differences
- We need a Finnish prefLabel
- We want to use the classes as groups
- As [skos:Collection is disjoint with skos:Concept](https://www.w3.org/TR/skos-reference/#L7130) we would not create exactMatch to honrnbostelandsachs: because they are of type skos:Concept

```
hornbostelandsachs:1  a skos:Concept ;
  skos:prefLabel "Idiophones"@en ;
  skos:inScheme <http://www.mimo-db.eu/HornbostelAndSachs#> ;
  skos:topConceptOf <http://www.mimo-db.eu/HornbostelAndSachs#> ;
  skos:notation "1" .
```

**Example of possible coding:**  
```
sekogroup:1 a skos:Collection, skos-thes:ConceptGroup ;   
  skos:prefLabel "Idiofonit"@fi ;
  skos:notation "1" ;
  skos:inScheme sekogroup:
  skos:relatedMatch hornbostelandsachs:1  ;  
  skos-thes:subGroup sekoclass:57, sekoclass:6204, sekoclass:2, sekoclass:83, sekoclass:70, sekoclass:6209 ;
  skos:narrowMatch hornbostelandsachs:57, hornbostelandsachs:6204, hornbostelandsachs:2,   
  hornbostelandsachs:83, hornbostelandsachs:70, hornbostelandsachs:6209 ;
  skos:member seko:00627 ;
 ```
- Use type skos-thes:ConceptGroup with skos-thes:subGroup and skos-thes:superGroup
- or skos-thes:ThesaurusArray (with skos-thes:subOrdinate and skos-thes:superOrdinate
 
Note! MIMO classification scheme models the relationship from the classification class to the instruments in the other schema with skos:exactMatch. which might not be the correct way?
Using groups and member: relationships might be a safer way.

## In case no Finnish language classification is accomplished
Easy solution would be to create for each instrument of seko: concept scheme:
- **skos:notation** for the H-S classification
- **skos:relatedMatch** mapping to the corresponding `hornbostelandsachs`: concept.

## Research
- The **KNIGHT REVISION of HORNBOSTEL-SACHS:** a new look at musical instrument classification by Roderic C. Knight, Professor of Ethnomusicology Oberlin College Conservatory of Music, © 2015, Rev. 2017. [https://www2.oberlin.edu/faculty/rknight/Organology/KnightRev2015.pdf](https://www2.oberlin.edu/faculty/rknight/Organology/KnightRev2015.pdf) 44 pages. (Retrieved 2026-07-20)
   - [15 References in Google Scholar](https://scholar.google.fi/scholar?cites=12007592548128174630&as_sdt=2005&sciodt=0,5&hl=fi)
   - journal article: RODERIC KNIGHT (2016) A New Look at Classification and Terminology for Musical Instruments. The Galpin Society Journal, Vol. 69 (April 2016), pp. 5-22, 154-155 (20 pages), Published By: Galpin Society - [https://www.jstor.org/stable/44083282](https://www.jstor.org/stable/44083282)
   - Professor emeritus, still active Personal homepage  https://theconversation.com/profiles/roderic-knight-1551309 (Retrieved 20-07-20)
   
- Citation:  Lee, D. (2019). Hornbostel-Sachs Classification of Musical Instruments. Knowledge Organization, 47(1), pp. 72-91.
   - doi: 10.5771/0943-7444-2020-1-72
   - https://www.imrpress.com/journal/KO/47/1/10.5771/0943-7444-2020-1-72
   - https://openaccess.city.ac.uk/id/eprint/22554/1/IEKO%2520Hornbostel-Sachs%2520VERSION%2520FOR%2520KO%2520post%2520minor%2520revision.pdf
