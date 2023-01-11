# SEKO
Translation project of <a href="https://finto.fi/seko/fi/">SEKO</a>, the Finnish medium of performance vocabulary.
Purpose - to add Swedish and English <b>skos:prefLabel</b> and links to corresponding concepts in <a href="https://finto.fi/yso/en/">YSO</a>, and Library of Congress Medium of Performance Thesaurus for Music <a href="https://id.loc.gov/authorities/performanceMediums.html">LCMPT</a> and to <a href="https://w.wiki/5jrV">Wikidata</a> items with the corresponding <a href="https://www.wikidata.org/wiki/Property:P10063">SEKO-ID (P10063)</a>. 

Note! The list of instument names in Swedish is lacking - sources needed.

# Sources for labels
* LCMPT - https://id.loc.gov/authorities/performanceMediums.html
* Wikidata - https://w.wiki/6Cn8
* Grove Music Online - https://www.oxfordmusiconline.com/grovemusic
* MusicBrainz Instrument -  https://musicbrainz.org/doc/Instrument
* MIMO - https://mimo-international.com/MIMO/
* hoorn.be - https://hoorn.be
* Ethnomusicology https://content.lib.washington.edu/ethnomusicweb/

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
