# SEKO3
Voluntary translation project of <a href="https://finto.fi/seko/fi/">SEKO</a>, the Finnish medium of performance vocabulary.

Working title: "Suomalainen esityskokoonpano-ontologia", "Finnish Medium of Performance Ontology"

### Project objective
To develop a trilingual linked data ontology of instruments and ensembles.  
The project procees is done in accordance with the Muusa expert group on music metadata.  

### Purpose
To help the Finnish GLAM network of libraries and museum collections to do music content description more easily and to increase interoprability of the vocabulary by adding Swedish and English labels <b>skos:prefLabel</b> and mappings to corresponding concepts in <a href="https://w.wiki/5jrV">Wikidata</a>, Library of Congress Medium of Performance Thesaurus for Music <a href="https://id.loc.gov/authorities/performanceMediums.html">LCMPT</a>, <a href="https://finto.fi/yso/en/">YSO-ontology</a>, and [MIMO thesaurus](https://vocabulary.mimo-international.com/InstrumentsKeywords/en/). 

"Finto-palvelun ontologiat ja sanastot musiikinkuvailussa" - presentation in 2021 <a href="https://doi.org/10.5281/zenodo.21360307">10.5281/zenodo.21360307</a>.

During the process we map items in Wikidata with the corresponding <a href="https://www.wikidata.org/wiki/Property:P10063">SEKO-ID (P10063)</a>. See also other identifiers in Wikidata <a href="http://www.wikidata.org/entity/P8516">LCMPT ID (P8516)</a> and <a href="http://www.wikidata.org/entity/P3763">MIMO instrument ID (P3763)</a>, <a href="http://www.wikidata.org/entity/P11214">UNIMARC: Medium of Performance ID (P11214)</a>, <a href="https://www.wikidata.org/entity/P1330">MusicBrainz instrument ID (P1330)</a>. 

Spatial information in the Seko instrument descriptions will be added as linked data using YSO-places ontology, Wikidata or Geospaces.

The datasest will consist of some 1200-1300 concepts of musical instruments and ensembles.   
Funding applications pending. Contact Jarmo Saarikko if you are interested in joining or sharing your expertise.  

### Documentation
[Datamodel](datamodel/README.md)  
[Masterdata structure](masterdata/README.md)  
[New and deprecated concepts in Masterdata](doc/README.md)   
[(Classifications(classification/README.md)  
[Sources for music instruments and their labels](https://github.com/NatLibFi/SEKO/wiki/0.02-Sources-for-music-instruments-and-their-labels)  
[Wiki](https://github.com/NatLibFi/SEKO/wiki/) (guidelines, plans, etc)  
[Soitinnimien ohjeluettelo (2017)](https://github.com/NatLibFi/SEKO/wiki/9-Aidatrumpetista-zimbalomiin) (copy of archived version)  

## Activites
2026-07
- All planned issues on problematic instruments or those without mappings have been created.  On 2026-07-05 there are 141 "open" issues and 30 "solved". The unfinished masterdata backup was uploaded as a CSV file to the repository. Created a description of the columns in the masterata table (masterdata.md) and added a description of the data model in  the wiki section.
- The [MIMO vocabulary](https://vocabulary.mimo-international.com/en/about) was contacted concerning data download and Finnish labels. 
- **Sources for labels** The list was updated with additional sources and moved to the Seko Wiki (see the link above) - See also the list of printed sources used in the original Seko vocabulary. <a target="_self" href="https://github.com/NatLibFi/SEKO/wiki/K%C3%A4ytt%C3%B6ohjeet-Aidatrumpetista-zimbalomiin--sanastolle#l%C3%A4hdeluettelo">Lähdeluettelo</a>
- The Finnish Expert Group on Music Metadata **MUUSA**  decisions on SEKO concepts during 2021-01/2026-06 have been copied from their [wiki list](https://www.kiwi.fi/spaces/muusa/pages/106333360/Valmiit) to here as issues and marked with the label [MUUSA](https://github.com/NatLibFi/SEKO/issues?q=is%3Aissue%20label%3AMUUSA).
   - **Please note** that their decisions on SEKO concepts before 2019 are documented in the SEKO wiki on page <a href="https://github.com/NatLibFi/SEKO/wiki/Timeline-of-decisions-and-changes-in-the-SEKO-vocabulary-and-its-predecessor-Aidatrumpetista-zimbalomiin">Timeline of decisions and changes in the SEKO vocabulary and its predecessor Aidatrumpetista zimbalomiin</a>.
   - Both of these are now stored as `skos:historyNote` values in a separate ttl-file in the masterdata -folder. 
- Imported the predecessor "Soitinnimien ohjeluettelo" laast version (Oct, 2017) from Web Archive. Will post it in the Wiki. Downloaded also the first online version of 2002 from Web Archive. 
- Added documentation in the Wiki section about the planned new Data Model of SEKO3, SPARQL searching in Finto (and later Wikidata), list of concepts set for deprecation, plans for properties, added more items to the list of information source resources,  etc.
- Improved usability of the repository by creating subdirectories "doc", "datamodel" and "masterdata". Moved the datamodel documentation from wiki.
- started documenting SPARQL queries in th Wiki section. E.g. all skos:note field values of in Seko at finto.fi  into a table, etc.
- The issues in which the instruments were missing a Swedish prefLabel were labelled `svenskt namn saknas` and those missing a mapping to `wikidata`.
- Wrote a short intermediary status report which was sent to the Muusa group.
- Createad an AI-generated status report of the masterdata-table (with Claude Sonnet 5) - still adusting. Visible in the Wiki section Väliraportti as a PDF. Created also Claude skills for retrieving instrument information from various sources and  for instrument comparisons.
- Created an issue label `AI-generated` for specifying the issues which have comments that include AI-generated content.
- Created a `seko-metadata.ttl` in the datamodel directory for the new ontology schema metadata.  Created issue #185  about the description of the ontology in Swedish and English and also a `Milestone` for issues that are related to the whole ontology.
- Took the current skos:note values (descriptions) via the finto.fi API and added them into the masterdata-table as a separate column in preparation for updates, and translations as well as for checking the spatial and temporal information.
- Created a sub-project folder for instrument [classification](classification/README.md).
  
2006-06:
- As of June 2026 the list of instrument names in Swedish is lacking 58 labels. 57 English labels are missing.  MIMO may have some, but additional labels are needed.
- After handling all the open  issues here whe should have labels in 3 languages with a Wikidata-mapping for all current and some newly added items.
- During the editing some items will be DEPRECATED due to MERGE or other reasons. See the lists of planned <a href="./doc/deprecated-concepts.md">deprecations</a> and <a href="./doc/new-concepts.md">addtions</a>.

2023-05 
- Note! There are several possibly problematic concepts due to overlapping distribution of the same or similar instruments over several cultural and linguistic regions. Some concepts may need to be split up and some others should be joined to a single concept. These will be brought up as issues where they can be then discussed. See the list at Issue(https://github.com/NatLibFi/SEKO/issues)

## Data model of the vocabulary / ontology
- The Seko datamodel (classes and properties) is still work in progress. At first, the ontology will be a simple hierarchy, with mappings to other vocabularies and datasets when PIDs are available and to other external sources.
- The hierarchy matches closely the Hornboschel-Sachs classification.
- The datamodel will be documented in SKOS turtle format.
- See the separate [Datamodel](datamodel/README.md) description page.

## Mappings
The [skos:MappingRelations](https://www.w3.org/TR/skos-reference/#mapping) properties will be used to link to external sources. Preferrably with exactMatch, but also closeMatch, broadMatch and narrowMatch may be used when an exact match is not available.  

Current plan is to map to Wikidata and  several external authhority files. Wikidata mapping would be considered mandatory. The existing LCMPT mappings are checked and their coverage extended.
- Primary targets are Wikidata, YSO, LCMPT
- Secondary targets are  MIMO, Hornboschel-Sachs classification (maintained by MIMO).
- Other possible targets are Getty AAT
- Links to describing sources may be added with the seeAlso property.

## Library data: BIBFRAME and MARC21

For content description purposes the appropriate concepts in SEKO3 could be marked as instances of <b><a href="https://id.loc.gov/ontologies/bibframe.html#c_MusicEnsemble">bf:MusicEnsemble</a></b>  or <b><a href="https://id.loc.gov/ontologies/bibframe.html#c_MusicInstrument">bf:MusicInstrument</a></b> or <a href="https://id.loc.gov/ontologies/bibframe.html#c_MusicMedium">bf:MusicMedium</a></b>. This is still under consideration.

In MARC21 data recoreds they can be used in the [382 field](https://www.loc.gov/marc/bibliographic/bd382.html)
The [MARC21 source code](https://www.loc.gov/standards/sourcelist/musical-instrumentation.html) for the vocabulary is "**seko**" 

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
* The editorial unfinished work in progress on the new multilingual SEKO3 version may be viewed "live" in the Google sheets. Occasionally we may take snapshots of this file in CSV format. This dataset is not yet available in RDF format. 
  * Live view: [masterdata-table](https://docs.google.com/spreadsheets/d/e/2PACX-1vTEDuG_WbvotPxd9TYSTpewOw5m7qXenPWH3Ei-a4bu51qPYOwkdgnK70fq4F_LTfBOKajJUdOeoR3G/pubhtml?gid=2068134809&single=true) (5200+ rows, 31 columns)
