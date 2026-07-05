# SEKO3
Voluntary translation project of <a href="https://finto.fi/seko/fi/">SEKO</a>, the Finnish medium of performance vocabulary.
Purpose - to add Swedish and English <b>skos:prefLabel</b> and links to corresponding concepts in <a href="https://finto.fi/yso/en/">YSO</a>, and Library of Congress Medium of Performance Thesaurus for Music <a href="https://id.loc.gov/authorities/performanceMediums.html">LCMPT</a> and to <a href="https://w.wiki/5jrV">Wikidata</a>   items with the corresponding <a href="https://www.wikidata.org/wiki/Property:P10063">SEKO-ID (P10063)</a>. See also <a href="http://www.wikidata.org/entity/P8516">LCMPT ID (P8516)</a> and <a href="http://www.wikidata.org/entity/P3763">MIMO instrument ID (P3763)</a>, <a href="http://www.wikidata.org/entity/P11214">UNIMARC: Medium of Performance ID (P11214)</a>, <a href="https://www.wikidata.org/entity/P1330">MusicBrainz instrument ID (P1330)</a>.  

As of 2026-06 the original live dataset is maintained in MARC21 and exported to skos format to Finto-data repository at
https://github.com/NatLibFi/Finto-data/tree/master/vocabularies/seko
The latest changes to the data were committed in 2021-09-28 and the metadata of the dataset was updated in 2025-05-21. 

Note! As of March 2023 the list of instrument names in Swedish is lacking 91 labels. 67 English labels are missing.  MIMO may have some, but additional labels are needed. 

Note! There are several possibly problematic concepts due to overlapping distribution of the same or similar instruments over several cultural and linguistic regions. Some concepts may need to be split up and some others should be joined to a single concept. These will be brought up as issues where they can be then discussed. See the list at https://github.com/NatLibFi/SEKO/issues

# Sources for labels
* LCMPT - https://id.loc.gov/authorities/performanceMediums.html
* UNIMARC: Medium of performance (mop) - https://www.iflastandards.info/unimarc/terms/mop?language=sv
  * Repository: https://github.com/iflastandards/unimarc/blob/master/ttl/ns/unimarc/terms/mop.ttl
* Wikidata - https://w.wiki/6Cn8
  * Wikidata - https://en.wikipedia.org/wiki/List_of_national_instruments_(music)
* Grove Music Online - https://www.oxfordmusiconline.com/grovemusic (paywall)
* Getty AAT Online search form https://www.getty.edu/research/tools/vocabularies/aat/?find=
* MusicBrainz Instrument -  https://musicbrainz.org/doc/Instrument
* MIMO - https://mimo-international.com/MIMO/
  * MIMO Thesaurus of musical instrument names https://vocabulary.mimo-international.com/InstrumentsKeywords/en/
* hoorn.be - https://hoorn.be
* Hello Music Theory https://hellomusictheory.com/learn/instruments/
* Ethnomusicology https://content.lib.washington.edu/ethnomusicweb/
* The Stringed Instrument Database https://stringedinstrumentdatabase.aornis.com/ (not updated, read 2026-07-05)
* Institute of Musical Instrument Technology https://www.imit.org.uk/pages/a-to-z-of-musical-instrument.html
* A to Z of percussion music https://www.percussion4u.co.uk/pages/a-to-z-of-percussion-instruments
* Cambridge UP: <a href="https://www.cambridge.org/core/books/abs/cambridge-encyclopedia-of-brass-instruments/selective-list-of-vernacular-horns-and-trumpets/C714FB2CC8CCDB80CB745436FE37CF1E">Appendix 1 - A Selective List of Vernacular Horns and Trumpets</a> (paywall)
* Archive.org <a href="https://archive.org/details/surveyofmusicali00marc">Marcuse, S. A survey of musical instruments</a> (registration required)
* Virginia Tech: <a href="https://web.archive.org/web/20060828221211/http://www.music.vt.edu/musicdictionary/appendix/instruments/instrumentmain.html">Comprehensive Table of Musical Instrument Classifications</a> (Web archive)
* Yale University Library (read 2026-07-03)
  * <a href="https://yalelibrary.atlassian.net/wiki/spaces/YMD/pages/202026619/Music+Cataloging+at+Yale">Music Cataloging at Yale</a> (many resources)
  * <a href="https://yalelibrary.atlassian.net/wiki/spaces/YMD/pages/202029664/When+is+a+flute+not+a+flute">When is a "flute" not a flute?"</a>
  * <a href="https://yalelibrary.atlassian.net/wiki/spaces/YMD/pages/202035904/Controlled+Vocabularies+for+Music+Cataloging">Controlled Vocabularies for Music Cataoging</a>
* Grinnell College Musical Instrument Collection https://omeka-s.grinnell.edu/s/MusicalInstruments/page/welcome (read 2026-07-05)
* University of Edinburg https://collections.ed.ac.uk/mimed/search/*:*/Collection:%22mimed+%7C%7C%7C+MIMEd%22 (read 2026-07-05)
* Instruments du Monde https://instruments-du-monde.com/en
* Europeana https://www.europeana.eu/fi/search?query=
* Murtomäki, Veijo 2006. Keskiajan ja renessanssin soittimet. Muhi – Musiikinhistoriaa verkossa, Taideyliopiston Sibelius-Akatemia. Verkkoaineisto https://muhi.uniarts.fi/kesk_ja_ren_soittimet/ (Read 2026-07-05).
* OnMusic Dictionary https://70.33.166.159/instruments/family/world (Note! Not safe connection) (Read 2026-07-05).
* Organology.net " A practical resource for musical instruments." - https://organology.net/instruments/ (855 on 2026-07-05)
* Dolmetsch music dictionary online https://www.dolmetsch.com/musictheorydefs.htm (read 2026-07-05)
* BnF Data: Instruments de musique https://data.bnf.fr/en/ark:/12148/cb119367821 (search or look at Narrower concepts) (read 2026-07-05)
* Wikipedia: List of national instruments (Music) https://en.wikipedia.org/wiki/List_of_national_instruments_(music)
* RIdIM Repertoire International d'Iconographie Musicale https://db.ridim.org/search.php - images with instruments (read 2026-07-05)
* Leisiö, T. (2010). Luonnollisten soitinten luokitusjärjestelmä. Toinen, uudistettu laitos. Musiikintutkimuksen laitos. https://www.yumpu.com/fi/document/view/5067218/luonnollisten-soitinten-luokitusjarjestelma-pdf/5

## Smaller datasets
### Europe
* Minna Hokka https://minnahokka.com/ - traditional Finnish wind instruments (read 2026-07-05)
* Edinburgh University Collection of Historic Musical Instruments https://collections.ed.ac.uk/mimed/
* Folkdance footnotes https://folkdancefootnotes.org/music/musical-instruments/ (Don Buskirk's blog)
* Traditional musical instruments of Latvia https://www.tautasmuzikasinstrumenti.lv/ (project page)
* A Primer on Latvian folk instruments https://latviansonline.com/a-primer-on-latvian-folk-instruments/ (read 2026-07-05)
* Musical Instruments in the Baltic Region http://www.music.lv/mukti/BalticMI.htm
* Traditional stringed instruments of Greece https://www.helleniccomserve.com/stringintruments.html
* Yves Moreau, 1975: Bulgarian folk music instruments https://socalfolkdance.org/articles/bulgarian_folk_music_instruments_moreau.htm (read 2026-07-05)
* Benjamin Schweitzer (2018) (Master's thesis) <a href="https://epub.ub.uni-greifswald.de/frontdoor/deliver/index/docId/3340/file/Schweitzer_Musikinstrumente_Finnisch.pdf">Musikinstrumentenbezeichnungen im Finnischen: Historisch-systematischer Überblick,  Varianten und Verstetigung</a> (PDF) (read 2026-07-05)
* Folkdance footnotes Beyond Choreography: 2. Instruments https://folkdancefootnotes.org/music/musical-instruments/ (read 2026-07-05)
### Asia
* Sound of Asia https://www.soundofasia.com/ (Commercial company)
* Terms in North Indian music https://chandrakantha.com/glossary/
* Dan Farrant: "12 Turkish instruments you should know" https://hellomusictheory.com/learn/turkish-instruments/
### Africa
* Percival Kirby Musical Instruments https://ibali.uct.ac.za/s/pkmi/ (University of Cape Town)
* DEKKMMA - Digitization project. The sound archive of the department of Ethnomusicology of the Royal Museum for Central Africa at Tervuren (Belgium).  https://music.africamuseum.be/english/index.html

And many more...

# BIBFRAME

For mapping purposes the appropriate concepts in SEKO3 could be marked as instances of <b><a href="https://id.loc.gov/ontologies/bibframe.html#c_MusicEnsemble">bf:MusicEnsemble</a></b>  or <b><a href="https://id.loc.gov/ontologies/bibframe.html#c_MusicInstrument">bf:MusicInstrument</a></b> or <br><a href="https://id.loc.gov/ontologies/bibframe.html#c_MusicMedium">bf:MusicMedium</a></b>. 

# Wikidata mappings

```sparql
# get all subclasses of "musical instrument" about 4300 and get identifiers from them
        SELECT DISTINCT ?item ?itemLabel ?SEKO_ID ?LCMPT_ID ?MIMO_ID ?MB_ID ?GMO_ID ?MOP_ID 
         WHERE {
           SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
           ?item wdt:P279+ wd:Q34379.
           OPTIONAL { ?item wdt:P10063 ?SEKO_ID. }
           OPTIONAL { ?item wdt:P8516 ?LCMPT_ID .}
           OPTIONAL { ?item wdt:P1330 ?MB_ID . }
           OPTIONAL { ?item wdt:P3763 ?MIMO_ID . }
           OPTIONAL { ?item wdt:P8591 ?GMO_ID . }
           OPTIONAL { ?item wdt:P11214 ?MOP_ID . }
         }
```  
- link to the above query https://w.wiki/6DFs 
- musical instrument http://www.wikidata.org/entity/Q34379
- Hornbostel-Sachs markings - sparql search on Wikidata https://w.wiki/6QPJ (2392 hits on 2026-07-05)

# Seko datasets
* Published monoligual dataset in RDF https://github.com/NatLibFi/Finto-data/tree/master/vocabularies/seko (tranformed from MARC dataset on Melinda)
* This editorial work in process: view the <a target="seko3" href="https://docs.google.com/spreadsheets/d/1pJH3UghucVpFdedI6F1QzHYE_kQMWmGe2wTm2LvYX4w/edit?usp=sharing">masterdata Google sheet</a>
