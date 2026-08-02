# SEKO3
Voluntary project on developing <a href="https://finto.fi/seko/fi/">SEKO</a>, the Finnish medium of performance vocabulary into an service with a multilingual linked data ontology and classification.

Project title: "SEKO3 – Musiikin kulttuuriperinnön yhteentoimivat tietoaineistot"

### Project objective
To develop a long-term service to support Finnish music content and instrument description based on a trilingual linked data ontology of instruments and ensembles with adding a Finnish language version of an instrument classification. 

Working titles for the service:
- "Suomalainen esityskokoonpano-ontologia" 
- "Finsk ontologi för  musikbesättning"
- "Finnish Medium of Performance Ontology"

### Purpose
To help the Finnish GLAM network of libraries and museum collections to do music content description more easily and to increase interoprability of the vocabulary and collections by adding Swedish and English labels and mappings to corresponding concepts in <a href="https://w.wiki/5jrV">Wikidata</a>, Library of Congress Medium of Performance Thesaurus for Music <a href="https://id.loc.gov/authorities/performanceMediums.html">LCMPT</a>, <a href="https://finto.fi/yso/en/">YSO-ontology</a>, and [MIMO thesaurus](https://vocabulary.mimo-international.com/InstrumentsKeywords/en/). 

Specific emphasis will be based on covering Finnish musical instruments extensively to support the preservation of the Finnish cultural heritage.

The project process is done in accordance with the Finnish expert group on music metadata (MUUSA).

See also "Finto-palvelun ontologiat ja sanastot musiikinkuvailussa" - presentation in 2021 <a href="https://doi.org/10.5281/zenodo.21360307">10.5281/zenodo.21360307</a>.

During the process we map items in Wikidata with the corresponding <a href="https://www.wikidata.org/wiki/Property:P10063">SEKO-ID (P10063)</a>. See also other identifiers in Wikidata <a href="http://www.wikidata.org/entity/P8516">LCMPT ID (P8516)</a> and <a href="http://www.wikidata.org/entity/P3763">MIMO instrument ID (P3763)</a>, <a href="http://www.wikidata.org/entity/P11214">UNIMARC: Medium of Performance ID (P11214)</a>, <a href="https://www.wikidata.org/entity/P1330">MusicBrainz instrument ID (P1330)</a>. 

Specific information inside the current Seko instrument descriptions will be entered as structured linked data using e.g. YSO, YSO time, YSO-places ontologyies, Wikidata or Geospaces, etc.

The dataset will consist of some 1200-1500 concepts of musical instruments and ensembles.
The classification would be based on the MIMO dataset from 2011 and its addtions in 2018. 

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
 **<a id="previous">Go to</a>** [previous activities log](./activitynotes.md)

### 2026-08 AUGUST
**Week 32**
- Networking, planning, documenting


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

## Museums and Archives
- As the museums are already using KOKO ontology, one easy option would be to include SEKO3 to KOKO
- As SEKO is not an YSO-based ontology. What would be needed to be able to be included in KOKO?
- Archives - connections not known at the moment 

## Seko datasets
* The content and structure of the current monolingual Seko dataset is decided by the [Finnish Expert Group on Music Metadata (MUUSA)](https://www.kiwi.fi/spaces/muusa/pages/91751314/Musiikin+metatiedon+asiantuntijaryhm%C3%A4+Muusa).
* As of 2026-06 the original dataset is maintained as MARC21 Authority files on the national metadata repository Melinda (ALEPH library system) hosted by the National Library of Finland. The data is transformed and exported in SKOS format (RDF) to Finto-data repository at https://github.com/NatLibFi/Finto-data/tree/master/vocabularies/seko. This data is browsable through the Finto service https://finto.fi/seko/en/ (a Skosmos syste,). The latest changes to the data were committed in 2021-09-28 and the metadata of the whole dataset was updated in 2025-05-21. 
* The editorial unfinished work in progress on the new multilingual SEKO3 version may be viewed "live" in the Google sheets. Occasionally we may take snapshots of this file in CSV format. This dataset is not yet available in RDF format. 
  * Live view: [masterdata-table](https://docs.google.com/spreadsheets/d/e/2PACX-1vTEDuG_WbvotPxd9TYSTpewOw5m7qXenPWH3Ei-a4bu51qPYOwkdgnK70fq4F_LTfBOKajJUdOeoR3G/pubhtml?gid=2068134809&single=true) (5200+ rows, 31 columns)
