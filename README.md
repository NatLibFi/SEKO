# SEKO3
Voluntary translation project of <a href="https://finto.fi/seko/fi/">SEKO</a>, the Finnish medium of performance vocabulary.
Purpose - to add Swedish and English <b>skos:prefLabel</b> and links to corresponding concepts in <a href="https://finto.fi/yso/en/">YSO</a>, and Library of Congress Medium of Performance Thesaurus for Music <a href="https://id.loc.gov/authorities/performanceMediums.html">LCMPT</a> and to <a href="https://w.wiki/5jrV">Wikidata</a>   items with the corresponding <a href="https://www.wikidata.org/wiki/Property:P10063">SEKO-ID (P10063)</a>. See also <a href="http://www.wikidata.org/entity/P8516">LCMPT ID (P8516)</a> and <a href="http://www.wikidata.org/entity/P3763">MIMO instrument ID (P3763)</a>, <a href="http://www.wikidata.org/entity/P11214">UNIMARC: Medium of Performance ID (P11214)</a>, <a href="https://www.wikidata.org/entity/P1330">MusicBrainz instrument ID (P1330)</a>.  

## Activites
2026-07
- All planned issues on problematic instruments or those without mappings have been created.  On 2026-07-05 there are 141 "open" issues and 30 "solved". The unfinished masterdata backup was uploaded as a CSV file to the repository. Created a description of the columns in the masterata table (masterdata.md) and added a description of the data model in  the wiki section.
- The [MIMO vocabulary](https://vocabulary.mimo-international.com/en/about) was contacted concerning data download and Finnish labels. 
- **Sources for labels** The list was updated with additional sources and moved to the Seko Wiki-section <a target="_self" href="https://github.com/NatLibFi/SEKO/wiki/Sources-for-music-instruments-and-their-labels">Sources for music instruments and their labels</a>  -- See also the list of printed sources used in the original Seko vocabulary. <a target="_self" href="https://github.com/NatLibFi/SEKO/wiki/K%C3%A4ytt%C3%B6ohjeet-Aidatrumpetista-zimbalomiin--sanastolle#l%C3%A4hdeluettelo">Lähdeluettelo</a>
- The Finnish Expert Group on Music Metadata **MUUSA**  decisions on SEKO concepts during 2021-01/2026-06 have been copied from their [wiki list](https://www.kiwi.fi/spaces/muusa/pages/106333360/Valmiit) to here as issues and marked with the label [MUUSA](https://github.com/NatLibFi/SEKO/issues?q=is%3Aissue%20label%3AMUUSA).  **Please note** that their decisions on SEKO concepts before 2019 are documented in the SEKO wiki on page <a href="https://github.com/NatLibFi/SEKO/wiki/Timeline-of-decisions-and-changes-in-the-SEKO-vocabulary-and-its-predecessor-Aidatrumpetista-zimbalomiin">Timeline of decisions and changes in the SEKO vocabulary and its predecessor Aidatrumpetista zimbalomiin</a>.

2006-06:
- As of June 2026 the list of instrument names in Swedish is lacking 58 labels. 57 English labels are missing.  MIMO may have some, but additional labels are needed.
- After handling all the open  issues here whe should have labels in 3 languages with a Wikidata-mapping for all current and some newly added items.
- During the editing some items will be DEPRECATED due to MERGE or other reasons. See the <a href="https://github.com/NatLibFi/SEKO/wiki/List-of-deprecated-concepts">list of planned deprecations</a>.

2023-05 
- Note! There are several possibly problematic concepts due to overlapping distribution of the same or similar instruments over several cultural and linguistic regions. Some concepts may need to be split up and some others should be joined to a single concept. These will be brought up as issues where they can be then discussed. See the list at Issue(https://github.com/NatLibFi/SEKO/issues)

## Data model of the vocabulary / ontology
- The data model of Seko3 will be based on SKOS  turtle format. The model (classes and properties) is still work in progress. At first, it will be a simple hierarchy, with mappings to other vocabularies and datasets when PIDs are available. Current plan is to map to LCMPT, Wikidata, MIMO, possible Hornboschel-Sachs classification (maintained by MIMO).  [skos:MappingRelations](https://www.w3.org/TR/skos-reference/#mapping) will be used.
- Geographical information - Spatial references will be used to show the origin or usage area of the instrument if it can be identified (dct:spatial). The identifiers have not been decided. Most probably YSO-paikat, but maybe https://www.geonames.org/ or Wikidata might work, too.
Most other information useful in content description would be obtained through the corresponding wikidata item. E.g. link to an image of the instrument.
- Documentation - Additional external information about the instrument may be mapped with the [skos:related](https://www.w3.org/TR/skos-reference/#related) property.
- Collections - The [skos:Collection](https://www.w3.org/TR/skos-reference/#Collection) class may be used in some cases to show e.g. "folk instruments" where the instruments are spread out all around the hierarchy.


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
* The content and structure of the current monolingual Seko dataset is decided by the [Finnish Expert Group on Music Metadata (MUUSA)](https://www.kiwi.fi/spaces/muusa/pages/91751314/Musiikin+metatiedon+asiantuntijaryhm%C3%A4+Muusa).
* As of 2026-06 the original dataset is maintained as MARC21 Authority files on the national metadata repository Melinda (ALEPH library system) hosted by the National Library of Finland. The data is transformed and exported in SKOS format (RDF) to Finto-data repository at https://github.com/NatLibFi/Finto-data/tree/master/vocabularies/seko. This data is browsable through the Finto service https://finto.fi/seko/en/ (a Skosmos syste,). The latest changes to the data were committed in 2021-09-28 and the metadata of the whole dataset was updated in 2025-05-21. 
* The editorial unfinished work in progress on the new multilingual SEKO3 version may be viewed "live" in the <a target="seko3" href="https://docs.google.com/spreadsheets/d/1pJH3UghucVpFdedI6F1QzHYE_kQMWmGe2wTm2LvYX4w/edit?usp=sharing">masterdata Google sheet</a>.  Occasionally we may take snapshots of this file in CSV format. This dataset is not yet available in RDF format. 
