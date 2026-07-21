# SEKO3 datamodel
**Latest published version**  
    Not available

**This version**  
    0.1 / Jarmo Saarikko / first draft 

**Date**  
    2026-07-21  

**Creator**  
    Jarmo Saarikko  

**Editors**  
    Jarmo Saarikko  

**Other participants**  
    MUUSA group

**Version**  
    This model will be the official version. There may be other versions in other languages.  
    the RDF/turtle structure is heavily based on the YSO datamodel on finto.fi service  

**Copyright**  
    Jarmo Saarikko  

**License**  
    [<https://creativecommons.org/publicdomain/zero/1.0/>](https://creativecommons.org/licenses/by-nd/4.0/) - due to unfinshed work  


TOC  
1 Summary   
2 Availability    
3 Identifiers
4 Prefixes  
5 Conept map  
6 Concepts (owl:Class)  
7 Group concepts  
8 Schemes (skos:conceptScheme)  
9 List of features   
10 Term labels (rdfs:label)  
11 Semantic relationsships (skos:semanticRelation)  
12 Mapping relationshiops (skos:mappingRelation)  
13 Documentation (skos:Note)  
14 Properties of skos:ConceptScheme  
15 Other properties (rdf:Property)  
16 Development versions  
17 Change documentation  


## Summary    
SEKO3 ontology is an trilingual ontology of musical instruments and ensembles (medium of performance).  It is based on the monolinugal "Suomalainen esityskokoonpanosanasto" which was based on earlier vocabularies of instruments. It is aimed to support the description of music related resources and authority files in the GLAM sector. In library data it can be used in the 382 and 511 fields to describe the instruments and performers. The structure of the vocabulary as been renewed and added with mappings to other vocabularies to increase itse usability and interoperability. 

## 1 Introduction
The semantic datamodel is based on the [W3C SKOS-datamodel](https://www.w3.org/2004/02/skos/). This document will explain how the SKOS- and other RDF-datamodels, such as ISO 25964 **iso-thes** and **Dublin Core Terms** have been applied for the use in SEKO3.  

## 2 Availability    
This model is available at the National Library of Finland SEKO-repository on Github. 
The ontology is planned to replace the current monolingual vocabulary in the finto.fi service without any disturbance in the content description work.

The SEKO dataset can be used in library- museum- and other databases in the same way as other authority files. 
The maintenace of the dataset has been previously on and aleph library system in MARC21 Authority file format.

The future maintenance options are still open, but the [Finto VobBench](https://www.kiwi.fi/spaces/Finto/pages/546308216/VocBench+-editori) platform is a strong candidate.

## 3 Identifiers
The datamodel will be using prefixes for the frequently appearing indentfiers in the dataset.
#### Identifiers of the concepts
Each concept has a permanent identifier (PID) which follows the form:
`http://urn.fi/urn:nbn:fi:au:seko:NNNNN` where NNNNN is usually 5 to 6 digits. The N carries no meaning
Any deprecated concepts will remain in the dataset and usually will be forwarded to a remaining concept.

#### Identifiers of the Seko dataset
- The identifier of the SEKO dataset regiestered by the Library of Congress in the "Musical Instrumentation and Voice Code Source Codes" is: [seko](http://id.loc.gov/vocabulary/musiccodeschemes/seko)
- In Wikidata: "SEKO - Finnish medium of performance thesaurus" [Q106573395](http://www.wikidata.org/entity/Q106573395)
- URN: `urn:nbn:fi:au:seko:`
- Bartoc.org identifier [18435](https://bartoc.org/en/node/18435)

## 4 Prefixes  
The datamaodel uses classes and properties from several different vocabularies. In the data they are refeerred to with prefixes listed below. The "common" ontology prefixes used are
```
@prefix adms: <http://www.w3.org/ns/adms#> .
@prefix dc: <http://purl.org/dc/elements/1.1/> .
@prefix dct: <http://purl.org/dc/terms/> .
@prefix foaf: <http://xmlns.com/foaf/0.1/> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix rdau: <http://rdaregistry.info/Elements/u/> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix skos: <http://www.w3.org/2004/02/skos/core#> .
@prefix skos-thes: <http://purl.org/iso25964/skos-thes#> .
@prefix voaf <http://purl.org/vocommons/voaf#> .
@prefix xl <http://www.w3.org/2008/05/skos-xl#> .
@prefix xsd <http://www.w3.org/2001/XMLSchema#> .
@prefix xml: <http://www.w3.org/XML/1998/namespace> .
```

These specific "non-standard" prefixist will be used in addtion
```
@prefix bf: <http://id.loc.gov/ontologies/bibframe/> .                    # Bibframe datamodel
@prefix lcmpt: <http://id.loc.gov/authorities/performanceMediums/> .      # LC Medium of Performance Thesaurus
@prefix hornbostelandsachs: <http://www.mimo-db.eu/HornbostelAndSachs/> . # H-S classification, v2011
@prefix mimo: <http://www.mimo-db.eu/InstrumentsKeywords/> .              # MIMO instrument vocabulary
@prefix mstatus: <https://id.loc.gov/vocabulary/mstatus/> .               # status codes
@prefix seko: <http://urn.fi/urn:nbn:fi:au:seko:> .                       # seko dataset
@prefix seko-meta: <http://urn.fi/urn:nbn:fi:au:seko-meta:> .             # seko defintions
@prefix seko-issues: <https://github.com/NatLibFi/SEKO/issues/> .         # Github issues of SEKO3
@prefix yse-issue: <https://github.com/Finto-ehdotus/YSE/issues/> .       # Github issues of YSO
@prefix yso: <http://www.yso.fi/onto/yso/> .                              # YSO- and YSO places concepts
```

## 5 Conept map  
- under construction with low priority

## 6 Concepts (owl:Class)
Based on the YSO -datamodel, each concept may belong only to one of the four disjoint classes: general concepts, hierarchical/group concepts (and perhaps deprecated concept like in YSO  skosext:DeprecatedConcept)

Each instrument or ensemble has a type skos:Concept and either seko-meta:Instrument or seko-meta:Ensemble. A performer who is not classified as an "instrument" can be considered as an "ensemble" of size one.

Deprecated concepts are of type seko-meta:DeprecatedConcept and they have owl:deprecated "TRUE".

|Class|Type|Subclass|
|-|-|-|
|skos:ConceptScheme|owl:Class|-|
|skos:Collection|owl:Class|skos-thes:ThesaurusArray, skos-thes:ConceptGroup|
|skos:Concept|owl:Class|seko-meta:Concept, seko-meta:Hierarchy, seko-meta:Instrument, seko-meta:Ensemble|

||skos:concept|
|-|-|
|Label|Concept / Käsite|
|description|Top class for all conepts in the ontology|

||seko-meta:Instrument|
|-|-|
|Label|Instrument / Soitin |
|Description| Concept for grouping instruments |
|Note|Eeasier than doing with a specific Thesaurus Array|

- seko-meta:Ensemble
- seko-meta:Hierarchy
- seko-meta:DeprecatedConcept

**- TBC**

## 7 Group concepts  
- skos:Collection
- skos-thes:ConceptGroup
- skos-thes:ThesaurusArray

## 8 Schemes (skos:conceptScheme)
- skos:ConcptScheme

Schemes used in the dataset
- seko: -- includes seko-meta:Instrument and seko-meta:Ensemble concepts and their relations
- seko-meta: -- metadata of the ontology
- seko-group: -- place for for defining hieararchical and associative groups
   - Local Classification based on hornbostelandschs: (Concepts have exactMatch relationshiops)
   - Members can be either seko: or also mimo:  concepts

## 9 List of properties 
Range  (rdfs:range) us used fore describing that certain values of the object are instances of the class it is pointing to.  The property rdfs:range can also show the the values of the property are of certain type of literals. 

Domain (rdfs:domain) property shows that certain property is applied only with certain classes.  rdfs:domain is an instance of rdf:Property, which shows that any resource which has a named property is also an instance of one or more classes. 

|Property|rdfs:type|rdfs:domain|rdfs:range|
|-|-|-|-|
|dc:description|rdf:Property|skos:ConceptScheme|rdfs:Literal|
|TBC-|-|-|-|

## 10 Term labels (rdfs:label)  
The unit of information is a Concept. In ontologies the relationships between concepts are identified with unique URI-identifiers. The same concept may be referred to  with multiple different labels e.g. in different languages. The first form of presentation of a concept is their expression in a natural language: **labels**. SKOS provides three properties with which a term can be attached to a concept: `skos:prefLabel`, `skos:altLabel` and `skos:hiddenLabel`. Their type is rdf:Property.

- **skos:prefLabel**
  - Label: PREFERRED LABEL 
    Description:
- **skos:altLabel**
  - Label: ALTERNATIVE LABEL (entry term, variant)
    Description:
    Note: Within the ontology the same term can be an entry term for several concepts. Sometimes the entry term can be a preferred term in another vocabulary. Acronyms, plural and singular forms and terms in another language may be added as entry terms.  In the Seko dataset entry terms are represented in dozens of languages. If the language is not known it is marked either "und" or "en". In the turtle format the language is marked with a language tag in the form of "label"@de
    
. **skos:hiddenLabel**
  - Label: HIDEEN LABEL
    Description: -  
    Note: Usually misspelled labels, transcribed lables or labels without diacritics are added as entry terms. Also singular or plural forms of the preferred label can be entered.

## 11 Semantic relationsships (skos:semanticRelation)

### Herarchical and symmentric relations. 
- skos:broader - broader concept
- skos:narrower - narrower concept
- skos:related - associative concept
- skos:topConceptOf
- skos:hasTopCocenpt

### Group relationships
- skos:member
- dct:partOf
- skos:inScheme
- rdau:P60683 PREDECESSOR  (pending)
- rdau:P60686 FOLLOWER  (pending)
- dct:isReplacedBy

### Temporal and spatial coverage
- dct:spatial
- dct:temporal

## 12 Mapping relationshiops (skos:mappingRelation)
Mapping relationshiops are used for referring to concepts in other vocabularies. 
- skos:exactMatch
    - Note: The property skos:exactMatch is used to link two concepts, indicating a high degree of confidence that the concepts can be used interchangeably across a wide range of information retrieval applications.skos:exactMatch is a transitive property, and is a sub-property of skos:closeMatch. 
- skos:closeMatch
    - Note: he property skos:closeMatch is used to link two concepts that are sufficiently similar that they can be used interchangeably in some information retrieval applications. In order to avoid the possibility of "compound errors" when combining mappings across more than two concept schemes, skos:closeMatch is notdeclared to be a transitive property.
- skos:broadMatch
    - Note: The properties skos:broadMatch and skos:narrowMatch are used to state a hierarchical mapping link between two concepts. 
- skos:narrowMatch
    - Note: The properties skos:broadMatch and skos:narrowMatch are used to state a hierarchical mapping link between two concepts.  
- skos:relatedMatch
    - In YSO this is being used for referring from a deprecated concept to an active concept becaus the deprecated concepts are moved to a different schema reserved for the deprecated conepts only.

## 13 Documentation properties (skos:Note)

### Properties for Concepts
- skos:note
  - skos:definition
  - skos:scopeNote
  - skos:changeNote
  - skos:editorialNote
  - seko-meta:statusNote
- skos:notation
- dct:source
- dct:created
- dct:modified

## 14 Properties of skos:ConceptScheme
Planned Schemes: seko:, seko-groups: (e.g. for classification classes), seko-deprecated:
- dct:identifier
- dct:title
- dct:subject
- dct:relation
- rdfs:label
- skos:prefLabel
- dct:created
- dct:modified
- rdfs:comment
- dct:relation
- rdfs:type
- dct:creator
- dct:publisher
- dct:source 

## 15 Other properties (rdf:Property)
> https://www.w3.org/TR/owl-ref/#Property
> In addition to describing the specific classes of things they want to describe, user communities also need to be able to describe specific properties that characterize those classes of things. In RDF Schema, properties are described using the RDF class rdf:Property, and the RDF Schema properties rdfs:domain, rdfs:range, and rdfs:subPropertyOf. All properties in RDF are described as instances of class rdf:Property. 

### Properties for Property entities
Ontology specific internal ontologies are defined in the seko-meta.ttl file.
- rdfs:label
- rdfs:subPropertyOf
- 
### Properties for the ontolgoy
These are placed in the skeo-metadata.ttl file
- voaf:
- dct:
- dc:description	KUVAUS
    - Short description of the ontology (fi,sv,en)
- dc:title	NAME	The name of the Ontology
    - "SEKO esiintymiskokoopano-ontologia"@fi, "SEKO medium of performance ontology"@en
- dc:publisher	JULKAISIJA
    - "Kansalliskirjasto"@fi                         # change this to URI
- dc:creator
    - "Jarmo Saarikko", MUUSA                        # change these to URI
- dct:language
    - fi, sv, en                                     # change these to URI
- dct:LinguisticSystem	LANGUAGE	Käytetty kieli   # not used?
- dct:license	LICENSE	Ontologian lisenssit         # change this to URI
- dct:relation	RELATION
    - point to the SEKO vocabulary
- dct:subject
    - Music, Instruments, Ensembles, Medium of Performance #  change these to URIs

    

YSO-ontologian aihealue on yso:p1946
## 16 Development versions

## 17 Change documentation

 
    
    
