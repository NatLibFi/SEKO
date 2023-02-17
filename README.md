# SEKO
Translation project of <a href="https://finto.fi/seko/fi/">SEKO</a>, the Finnish medium of performance vocabulary.
Purpose - to add Swedish and English <b>skos:prefLabel</b> and links to corresponding concepts in <a href="https://finto.fi/yso/en/">YSO</a>, and Library of Congress Medium of Performance Thesaurus for Music <a href="https://id.loc.gov/authorities/performanceMediums.html">LCMPT</a> and to <a href="https://w.wiki/5jrV">Wikidata</a> items with the corresponding <a href="https://www.wikidata.org/wiki/Property:P10063">SEKO-ID (P10063)</a>. 

Note! The list of instument names in Swedish is lacking - sources needed.

# Sources for labels
* LCMPT - https://id.loc.gov/authorities/performanceMediums.html
* Wikidata - https://w.wiki/6Cn8
  * Wikidata - https://en.wikipedia.org/wiki/List_of_national_instruments_(music)
* Grove Music Online - https://www.oxfordmusiconline.com/grovemusic (paywall)
* MusicBrainz Instrument -  https://musicbrainz.org/doc/Instrument
* MIMO - https://mimo-international.com/MIMO/
  * Scenkonstmuseet <a href="https://mimo-international.com/mimo/detailstatic.aspx?RSC_BASE=IFD&RSC_DOCID=OAI_SMS_MM_POST_3381&TITLE=&_lg=sv-SE">Sinka</a>
* hoorn.be - https://hoorn.be
* Hello Music Theory https://hellomusictheory.com/learn/instruments/
* Ethnomusicology https://content.lib.washington.edu/ethnomusicweb/
* Institute of Musical Instrument Technology https://www.imit.org.uk/pages/a-to-z-of-musical-instrument.html
* A to Z of percussion music https://www.percussion4u.co.uk/pages/a-to-z-of-percussion-instruments
* Cambridge UP: <a href="https://www.cambridge.org/core/books/abs/cambridge-encyclopedia-of-brass-instruments/selective-list-of-vernacular-horns-and-trumpets/C714FB2CC8CCDB80CB745436FE37CF1E">Appendix 1 - A Selective List of Vernacular Horns and Trumpets</a> (paywall)
* Archive.org <a href="https://archive.org/details/surveyofmusicali00marc">Marcuse, S. A survey of musical instruments</a> (registration required)
* Virginia Tech: <a href="https://web.archive.org/web/20060828221211/http://www.music.vt.edu/musicdictionary/appendix/instruments/instrumentmain.html">Comprehensive Table of Musical Instrument Classifications</a> (Web archive)
* Smaller datasets
  * Europe
    * Minna Hokka https://minnahokka.com/ - traditional Finnish wind instruments
    * Edinburgh University Collection of Historic Musical Instruments https://collections.ed.ac.uk/mimed/
    * Folkdance footnotes https://folkdancefootnotes.org/music/musical-instruments/ (Don Buskirk's blog)
    * Traditional musical instruments of Latvia https://www.tautasmuzikasinstrumenti.lv/ (project page)
    * Musical Instruments in the Baltic Region http://www.music.lv/mukti/BalticMI.htm
    * Traditional stringed instruments of Greece https://www.helleniccomserve.com/stringintruments.html
  * Asia
    * Sound of Asia https://www.soundofasia.com/ (Commercial company)
    * Terms in North Indian music https://chandrakantha.com/glossary/

# Wikidata mappings

```sparql
# get all subclasses of "musical instrument" about 4300 and get identifiers from them
        SELECT DISTINCT ?item ?itemLabel ?SEKO_ID ?LCMPT_ID ?MIMO_ID ?MB_ID ?GMO_ID
         WHERE {
           SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
           ?item wdt:P279+ wd:Q34379.
           OPTIONAL { ?item wdt:P10063 ?SEKO_ID. }
           OPTIONAL { ?item wdt:P8516 ?LCMPT_ID .}
           OPTIONAL { ?item wdt:P1330 ?MB_ID . }
           OPTIONAL { ?item wdt:P3763 ?MIMO_ID . }
           OPTIONAL { ?item wdt:P8591 ?GMO_ID . }
         }
```  
- link to the above query https://w.wiki/6DFs 
- musical instrument http://www.wikidata.org/entity/Q34379
