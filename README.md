# SEKO3
Voluntary translation project of <a href="https://finto.fi/seko/fi/">SEKO</a>, the Finnish medium of performance vocabulary.

Working title: "Suomalainen esityskokoonpano-ontologia", "Finnish Medium of Performance Ontology"

### Project objective
To develop a trilingual linked data ontology of instruments and ensembles with optionally adding a Finnish language version of instrument classification. The project process is done in accordance with the Finnish expert group on music metadata (MUUSA).

### Purpose
To help the Finnish GLAM network of libraries and museum collections to do music content description more easily and to increase interoprability of the vocabulary by adding Swedish and English labels <b>skos:prefLabel</b> and mappings to corresponding concepts in <a href="https://w.wiki/5jrV">Wikidata</a>, Library of Congress Medium of Performance Thesaurus for Music <a href="https://id.loc.gov/authorities/performanceMediums.html">LCMPT</a>, <a href="https://finto.fi/yso/en/">YSO-ontology</a>, and [MIMO thesaurus](https://vocabulary.mimo-international.com/InstrumentsKeywords/en/). 

"Finto-palvelun ontologiat ja sanastot musiikinkuvailussa" - presentation in 2021 <a href="https://doi.org/10.5281/zenodo.21360307">10.5281/zenodo.21360307</a>.

During the process we map items in Wikidata with the corresponding <a href="https://www.wikidata.org/wiki/Property:P10063">SEKO-ID (P10063)</a>. See also other identifiers in Wikidata <a href="http://www.wikidata.org/entity/P8516">LCMPT ID (P8516)</a> and <a href="http://www.wikidata.org/entity/P3763">MIMO instrument ID (P3763)</a>, <a href="http://www.wikidata.org/entity/P11214">UNIMARC: Medium of Performance ID (P11214)</a>, <a href="https://www.wikidata.org/entity/P1330">MusicBrainz instrument ID (P1330)</a>. 

Spatial information in the Seko instrument descriptions will be added as linked data using YSO-places ontology, Wikidata or Geospaces.

The dataset will consist of some 1200-1300 concepts of musical instruments and ensembles.
The classification would be based on the MIMO dataset which has 643 classes. 
Funding applications pending. Contact Jarmo Saarikko if you are interested in joining or sharing your expertise.  

### Documentation
[Datamodel](datamodel/README.md)  
[Masterdata structure](masterdata/README.md)  
[New and deprecated concepts in Masterdata](doc/README.md)   
[Classification](classification/README.md)  
[Sources for music instruments and their labels](https://github.com/NatLibFi/SEKO/wiki/0.02-Sources-for-music-instruments-and-their-labels)  
[Wiki](https://github.com/NatLibFi/SEKO/wiki/) (guidelines, plans, etc)  
[Soitinnimien ohjeluettelo (2017)](https://github.com/NatLibFi/SEKO/wiki/9-Aidatrumpetista-zimbalomiin) (copy of archived version)  

## <a id="activities">Activites</a>
### 2026-07
**Week 30**
- Created a sub-project folder for instrument [classification](classification/README.md).  Uploaded a combination of both MIMO and Leisiö versions to OpenRefine. Added also narrower, broader and instrument links.
- Established a Github Project folder [SEKO3 project](https://github.com/orgs/NatLibFi/projects/62) to better manage the dozens of inssues and the project process. This will be under development for a while.
- continued checking the classification table for missing translations and mismatched notations. Mapped instruments mentioned by Leisio to seko: concepts. For those missing, created an issue with a list of them.
- started documenting the datamodel in a separate descriptive file (see the /datamodel folder) with the structure based on the YSO data model document.
- set the license to the model as [https://creativecommons.org/licenses/by-nd/4.0/](https://creativecommons.org/licenses/by-nd/4.0/) due to it being work in progress.
- continued working on the classification data. matching the addtional groups listed by Leisiö with the actual marking in the MIMO classification classes. Started finding translations for some of the labels.
- Started looking more closely at funding options. Need to write a realistic project plan, estimates of duration and budget.
- Created a separate list for [sources](./doc/sources.md) that would be referred in the data with `dct:source`. These could be sources for e.g. labels, definitions, spatial and temporal data. Added Finna URIs for printed sources used in the earlier version. Added finna: as a prefix.
- Added more sources for the classification page. Noticed the nice visual browser at [https://www.hornbostelsachs.com/](https://www.hornbostelsachs.com/).  
- Created v0.04 of the datamodel. Added ontology metadata. Created a new Top Concept seko:MediumOfPerformance with skos:narrower pointing to "instrument" and "performer". Documented deprecation idea in the model. Moved older notes to a separate file from this README.
- Moved the wikidata sparql section from this page to [SEKO3 Wiki](https://github.com/NatLibFi/SEKO/wiki/04-Tools-:-SPARQL)
- Created a separate `./mapping/` folder for holding mapping files.  Mapped SEKO3 concepts with the YKL library classification classes under [78 MUSIC](http://urn.fi/URN:NBN:fi:au:ykl:78) for the **145 instruments** or ensembles that were mentioned in the classnames or as entry terms.  Added four new concepts to the SEKO3 masterdata table.(jousisoitinsyntetisaattori, sähkökontrabasso, laulaja, jodlaus).

**Week 31**
- **Plan:** write project plan and documentation, map funding options, networking, work on 5-10 issues, start implementing the [SEKO3 Project section]([https://github.com/NatLibFi/SEKO/projects](https://github.com/orgs/NatLibFi/projects/62)).
- Completed translating all H-S class labels in Finnish (v.001).
    - Data is still only in a local Openrefine, but was able to export a RDF file in turtle format.
- Considered properties for "material" of instruments. Searched for vucabularies.
    - Created a folder "vocabulary" for a potential solution for any required lists of items (such as status codes and imstrument materials).  Created a demo vocabulary of "materials" with a AI-assistant based on data from Seko definitions.
    - There might be a potential to add these into Metadata vocabulary for a more general use?

 **<a id="previous">Go to</a>** [previous activities log](./activitynotes.md)

## Data model of the vocabulary / ontology
- The Seko datamodel (classes and properties) is still work in progress. At first, the ontology will be a simple hierarchy, with mappings to other vocabularies and datasets when PIDs are available and to other external sources.
- The hierarchy matches closely the Hornboschel-Sachs classification.
- The datamodel will be documented in SKOS turtle format.
- See the separate [Datamodel](datamodel/README.md) description page.

## Mappings
The [skos:MappingRelations](https://www.w3.org/TR/skos-reference/#mapping) properties will be used to link to external sources. Preferrably with exactMatch, but also closeMatch, broadMatch and narrowMatch may be used when an exact match is not available.  

Current plan is to map to Wikidata and  to an external authority file. Wikidata mapping would be considered mandatory. The existing LCMPT mappings are checked and their coverage extended.
- Primary targets are Wikidata, LCMPT, YSO
- Secondary targets are  MIMO instrument vocabulary, Hornboschel-Sachs classification (maintained by MIMO), KOKO.
- Other possible targets are Getty AAT (for instruments)
- Links to other sources describing the instrument and to help in content description may be added with the `rdfs:seeAlso` property.

## Library data: BIBFRAME and MARC21

For content description purposes the appropriate concepts in SEKO3 could be marked as instances of <b><a href="https://id.loc.gov/ontologies/bibframe.html#c_MusicEnsemble">bf:MusicEnsemble</a></b>  or <b><a href="https://id.loc.gov/ontologies/bibframe.html#c_MusicInstrument">bf:MusicInstrument</a></b> or <a href="https://id.loc.gov/ontologies/bibframe.html#c_MusicMedium">bf:MusicMedium</a></b>. 
- Classes  `seko:MusicInstrument` and `seko:MusicEnsemble` were added in version 0.04 of the datamodel and these were mapped to the corresponding Bibframe classes.

In MARC21 data records the labels of SEKO concepts can be used in the [382 field](https://www.loc.gov/marc/bibliographic/bd382.html) and other fields.
The [MARC21 source code](https://www.loc.gov/standards/sourcelist/musical-instrumentation.html) identifier for the vocabulary is "**seko**"  (subfield $2 value)

## Seko datasets
* The content and structure of the current monolingual Seko dataset is decided by the [Finnish Expert Group on Music Metadata (MUUSA)](https://www.kiwi.fi/spaces/muusa/pages/91751314/Musiikin+metatiedon+asiantuntijaryhm%C3%A4+Muusa).
* As of 2026-06 the original dataset is maintained as MARC21 Authority files on the national metadata repository Melinda (ALEPH library system) hosted by the National Library of Finland. The data is transformed and exported in SKOS format (RDF) to Finto-data repository at https://github.com/NatLibFi/Finto-data/tree/master/vocabularies/seko. This data is browsable through the Finto service https://finto.fi/seko/en/ (a Skosmos syste,). The latest changes to the data were committed in 2021-09-28 and the metadata of the whole dataset was updated in 2025-05-21. 
* The editorial unfinished work in progress on the new multilingual SEKO3 version may be viewed "live" in the Google sheets. Occasionally we may take snapshots of this file in CSV format. This dataset is not yet available in RDF format. 
  * Live view: [masterdata-table](https://docs.google.com/spreadsheets/d/e/2PACX-1vTEDuG_WbvotPxd9TYSTpewOw5m7qXenPWH3Ei-a4bu51qPYOwkdgnK70fq4F_LTfBOKajJUdOeoR3G/pubhtml?gid=2068134809&single=true) (5200+ rows, 31 columns)
