# SEKO3
Voluntary translation project of <a href="https://finto.fi/seko/fi/">SEKO</a>, the Finnish medium of performance vocabulary.
Purpose - to add Swedish and English <b>skos:prefLabel</b> and links to corresponding concepts in <a href="https://finto.fi/yso/en/">YSO</a>, and Library of Congress Medium of Performance Thesaurus for Music <a href="https://id.loc.gov/authorities/performanceMediums.html">LCMPT</a> and to <a href="https://w.wiki/5jrV">Wikidata</a>   items with the corresponding <a href="https://www.wikidata.org/wiki/Property:P10063">SEKO-ID (P10063)</a>. See also <a href="http://www.wikidata.org/entity/P8516">LCMPT ID (P8516)</a> and <a href="http://www.wikidata.org/entity/P3763">MIMO instrument ID (P3763)</a>, <a href="http://www.wikidata.org/entity/P11214">UNIMARC: Medium of Performance ID (P11214)</a>, <a href="https://www.wikidata.org/entity/P1330">MusicBrainz instrument ID (P1330)</a>.  

As of 2026-06 the original live dataset is maintained in MARC21 and exported to skos format to Finto-data repository at
https://github.com/NatLibFi/Finto-data/tree/master/vocabularies/seko
The latest changes to the data were committed in 2021-09-28 and the metadata of the dataset was updated in 2025-05-21. 

Note! As of June 2026 the list of instrument names in Swedish is lacking 58 labels. 57 English labels are missing.  MIMO may have some, but additional labels are needed. After handling all the open  issues here whe should have labels in 3 languages with a Wikidata-mapping for all current and some newly added items.  During the editing some items will be DEPRECATED due to MERGE or other reasons. See the <a href="https://github.com/NatLibFi/SEKO/wiki/List-of-deprecated-concepts">list of planned deprecations</a>.

Note! There are several possibly problematic concepts due to overlapping distribution of the same or similar instruments over several cultural and linguistic regions. Some concepts may need to be split up and some others should be joined to a single concept. These will be brought up as issues where they can be then discussed. See the list at https://github.com/NatLibFi/SEKO/issues

## Sources for labels
The list was moved to the Seko Wiki-section <a target="_self" href="https://github.com/NatLibFi/SEKO/wiki/Sources-for-music-instruments-and-their-labels">Sources for music instruments and their labels</a>  -- See also the list of printed sources used in the original Seko vocabulary. <a target="_self" href="https://github.com/NatLibFi/SEKO/wiki/K%C3%A4ytt%C3%B6ohjeet-Aidatrumpetista-zimbalomiin--sanastolle#l%C3%A4hdeluettelo">Lähdeluettelo</a>

## BIBFRAME

For mapping purposes the appropriate concepts in SEKO3 could be marked as instances of <b><a href="https://id.loc.gov/ontologies/bibframe.html#c_MusicEnsemble">bf:MusicEnsemble</a></b>  or <b><a href="https://id.loc.gov/ontologies/bibframe.html#c_MusicInstrument">bf:MusicInstrument</a></b> or <br><a href="https://id.loc.gov/ontologies/bibframe.html#c_MusicMedium">bf:MusicMedium</a></b>. 

## Wikidata mappings

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

## Seko datasets
* Published monoligual dataset in RDF https://github.com/NatLibFi/Finto-data/tree/master/vocabularies/seko (tranformed from MARC dataset on Melinda)
* This editorial work in process: view the <a target="seko3" href="https://docs.google.com/spreadsheets/d/1pJH3UghucVpFdedI6F1QzHYE_kQMWmGe2wTm2LvYX4w/edit?usp=sharing">masterdata Google sheet</a>
