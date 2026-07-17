SEKO3 datamodel planning

## Namespaces to be used
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
@prefix skos-thes <http://purl.org/iso25964/skos-thes> .
@prefix voaf <http://purl.org/vocommons/voaf#> .
@prefix xl <http://www.w3.org/2008/05/skos-xl#> .
@prefix xsd <http://www.w3.org/2001/XMLSchema#> .
@prefix xml: <http://www.w3.org/XML/1998/namespace> .

@prefix bf: <http://id.loc.gov/ontologies/bibframe/> .
@prefix lcmpt: <http://id.loc.gov/authorities/performanceMediums/> .
@prefix mimo: <http://www.mimo-db.eu/InstrumentsKeywords/> .
@prefix mstatus: <https://id.loc.gov/vocabulary/mstatus/> .
@prefix seko: <http://urn.fi/urn:nbn:fi:au:seko:> .
@prefix seko-meta: <http://urn.fi/urn:nbn:fi:au:seko-meta/> .
@prefix seko-issues: <https://github.com/NatLibFi/SEKO/issues/> .
@prefix yse-issue: <https://github.com/Finto-ehdotus/YSE/issues/> .
@prefix yso: <http://www.yso.fi/onto/yso/> .
```

## Classes and properties to be used
### owl:
- owl:Class, owl:ObjectProperty, owl:DatatypePropety, owl:AnnotationProperty, owl:TransitiveProperty, owl:inverseOf, owl:Ontology, owl:Thing
owl:differentFrom, owl:imports, owl:sameAs, owl:versionInfo, owl:versionIRI, 


### rdf: rdfs:
- rdf:langString, rdf:Property, rdf:PlainLiteral
- rdf:type, rdf:subject, rdf:object, rdf:language
- rdfs:Datatype, rdfs:Resource, rdfs:Class, rdfs:Label, rdfs:Literal
- rdfs:domain, rdfs:range, rdfs:subClassOf, rdfs:subPropertyOf, rdfs:identifedBy
- **rdfs:comment** # used for giving a human readable label for a object URI
- **rdfs:seeAlso**  # Used for addtional external documentation describing the instrument or   
    other information useful in content description, e.g. link to an image of the instrument. See [UsingSeeAlso](https://www.w3.org/wiki/UsingSeeAlso).

### dc: dct:
for the ConceptScheme
- dc:coverage, dc:creator, dc:format, dc:publisher, dc:title, dc:type
- dct:accessRights, dct:rights, dct:abstract, dct:accrualMethod, dct:accrualPeriodicity, dct:accrualPolicy, dct:audience, dct:available, dct:bibliographicCitation, dct:conformsTo, dct:contributor, dct:coverage, dct:creator, dct:language, dct:license, dct:mediator, dct:publisher, dct:subject, dct:title, dct:type

for a Concept
- dct:description  #  string - short description of the concept --- USE skos:definition instead # 
- dc:source  # link to any source where a label or a definition was taken or confirmed
- dct:date  # Genreally not used
- dct:dateSubitted  # Used for the date a suggestion for the Concept was received
- dct:dateAccepted # Used for the date of approval by MUUSA or other group
- dct:created  # Used for date of creation of the skos:Conceopt in the dataset # MAINDATORY
- dct:valid  # Used for the date when the record became valid (minimum properties) but not accpeted by the editorial group
- dct:issued   # Used for the date of the Concept in a published version of the vocabulary
- dct:modified # Used for date of any logged modification of the Concept
- dct:relation # Used for linking to seko-issue:s and yse-issues:  
- dct:replaces  # Used for linking from a valid concept to a deprecated concept in the vocabulary
- dct:isReplacedBy # Used for linking from a deprecated concept to a replacing concept in the vocabulary (e.g.due to a merge or delete)
- dct:refernces # Used for linking to a source which is not used directly but may infuence the Concept data decisions (URI)
- dct:identifier  # seko-identifier of the concept (full URI) 
- dct:spatial  # Used for spatial origin or distribution or usage area of the Concept. Preferably a YSO-places URI. (can be a Wikidata or Geospaces URI)
- dct:temporal  # Used for temoporal era for a historical instrument when it was invented or used. Preferably YSO-aika URI (can be a wikidata URI)

### skos:
owl:Class:
- **skos:Concept**  #  Used for any instrument or ensemble element
- **skos:ConceptScheme**  #  Currently two schemes  seko: for the ontology and seko-meta: for the local class and property descriptions
- [skos:Collection](https://www.w3.org/TR/skos-reference/#Collection) # Used for grouping concepts, e.g. folk instruments, from different branches of the hierarchy.

Object Properties: 
- **skos:hasTopConcept**  # Used for the concept scheme.  Links to concepts that have no skos:broader properties
- **skos:member** #   Used for linking from a skos:Collection to its members
- **skos:inScheme**  # Used for skos:Concept to show which scheme (a vocabulary) it belongs to, a MANDATORY property for skos:Concept
- **skos:topConceptOf**  # Used for linking the top concept to the scheme it is a top concept of
- **skos:broader**  # Used for linking to hierarchically nearest broader concepts. There can be more than one.
- **skos:narrower** # Used for linking to the hierarchically nearest narrower conecpts, opposite to skos:broader
- **skos:related**  # Used for linking to a related skos:Cconcept WITHIN Seko but is not hierarchically broader or narrower
- skos:memberList  # currently not used

Datatype properties:
- **skos:notation**  #  Used for a alphanumeric label identifying e.g. a classification category. Not the same as identifier.

Annotation properties:
- **skos:altLabel** Used for all entry terms,  an language tag should be used to present the language if know. If not known, use "en" or "und"
- **skos:hiddenLabel**  # Used for plural/singular forms, misspellings, transcribed or non transcribed labels
- **skos:prefLabel** # Used for preferred label, only one per language. A MANDATORY property for skos:Concept
- **skos:note** #  Used for a general public note
- **skos:changeNote** # Used for a public note explainging any changes in the concept
- **skos:scopeNote**  # Used for a public note defining the use of the concept
- **skos:historyNote** # Used for a public note telling historical information of the concept record
- **skos:editorialNote** # Used for a non-visible note for the editorial process
- **skos:definition** # Used for describing features and how this instrument differs from others, may give spatial and temporal information
- skos:example  #  not used for the moment

Mapping properties:
- skos:mappingRelation, **skos:closeMatch**, **skos:exactMatch**, **skos:broadMatch**, **skos:narrowMatch**, **skos:relatedMatch**
  - Used for mapping Seko concepts to the same or similar concepts in external vocabularies

### skos-thes: - for the thesaurus / ontology  metadata

### skos-xl, xl:
- Still considered. Is used by YSO Ontology.

### xsd
xsd:integer, xsd:date, xsd:dateTime

### voaf
- voaf:Vocabulary, voaf:VocabularySpace
- voaf:extends, voaf:propertyNumber, voaf:classNumber, voaf:specializes, voaf:similar, voaf:toDoList

### SEKO
Note!  will add to seko-metadata.ttl a new annotation property: ****seko:statusNote**** as a subProperty of skos:note .
Planned prefix is **seko-meta:**
```
seko:statusNote a owl:AnnotationProperty ;
    rdfs:subPropertyOf skos:note ;
    rdfs:label "Tietueen tila"@fi, "Seko concept status"@en ;
    rdfs:range rdfs:Literal ;
    ddfs:domain rdfs:Resource ;
    skos:definition "A note intended strictly for Seko internal use."@en ;
    skos:scopeNote "Select value from: submitted, accepted, valid, deprecated, superceded, retired" ;
    skos:editorialNote "Only one value per record at any time.",
                       "Change and its reason should be registered in a skos:editorialNote" ;
    dct:source  https://dd.eionet.europa.eu/vocabulary/datadictionary/status/view  .
```
***Value vocabulary for the `seko-meta:statusNote` property***
- these are subject to change, this is a **preliminary suggestion** for usage in the masterdata table.
- Proposal for definitions of the "status" values for SEKO3. 
- The values may be need the simultaneous addition of a ``dct:date`` or one of its subProperties.

Select one value of:
- **submitted** 
    - for a submitted new concept, or a concept requiring a modification or a decision by MUUSA etc (``dct:dateSubmitted`` - for a new concept)
- **stable** 
    - the item is "valid" and "stable" and ok to be issued and published.
    - The entry is "live", but not specificly gone through the expert group decision process.
      (``dct:created``, ``dct:issued``, ``dct:available``, ``dct:modified``)
- **accepted** 
    - the concept or a change to it was accepted to be entered into the dataset by the expert group decision process (``dct:dateAccepted``)
- **deprecated** 
    - The item is deprecated but the follow-up is undecided  (``dct:modified``)
- **superceded** 
    - The item is deprecated and redirected to another item (``dct:modified``)
- **retired** 
    - The item is deprecated and deleted from use, no redirection. (``dct:modified``)
- **valid**
    - The value "valid" usually means the time range when a value is valid and true. E.g. for a time range. (``dct:valid``)

A second option could be to use the MARC [Status codes](http://id.loc.gov/vocabulary/mstatus)
- Codes and term sources to indicate the status of a resource.

## Concept minimum content
For any concept the **minimum** set of properties is:
- rdfs:type
- skos:prefLabel
- dct:identifier
- skos:broader (or skos:topConeptOf)
- skos:exactMatch 

## Example of a fuller concept data

`TBC`



