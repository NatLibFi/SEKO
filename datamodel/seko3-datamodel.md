
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
@prefix seko-issue: <https://github.com/NatLibFi/SEKO/issues/> .
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
- rdfs:domain, rdfs:range, rdfs:comment, rdfs:subClassOf, rdfs:subPropertyOf, rdfs:comment, rdfs:identifedBy
- rdfs:seeAlso  (read more at https://www.w3.org/wiki/UsingSeeAlso)

### dc: dct:
for the ConceptScheme
- dc:coverage, dc:creator, dc:format, dc:publisher, dc:title, dc:type
- dct:accessRights, dct:rights, dct:abstract, dct:accrualMethod, dct:accrualPeriodicity, dct:accrualPolicy, dct:audience, dct:available, dct:bibliographicCitation, dct:conformsTo, dct:contributor, dct:coverage, dct:creator, dct:language, dct:license, dct:mediator, dct:publisher, dct:subject, dct:title, dct:type

for a Concept
- dct:created, dct:issued, dct:modified,  dct:dateAccepted, dct:dateSubitted, dct:date, dct:valid
- dc:source, dct:relation, dct:isReplacedBy, dct:replaces, dct:refernces, dct:description, dct:identifier, dct:spatial, dct:temporal

### skos:
Classes:
- skos:Concept, skos:ConceptScheme

Object Properties: 
- skos:hasTopConcept, skos:member, skos:inScheme, skos:topConceptOf, skos:broader, skos:narrower, skos:related, skos:memberList

Datatype properties:
- skos:notation  

Annotation properties:
- skos:altLabel, skos:hiddenLabel, skos:prefLabel
- skos:note, skos:changeNote, skos:definition, skos:editorialNote, skos:example, skos:historyNote, skos:scopeNote

Mapping properties:
- skos:mappingRelation, skos:closeMatch, skos:exactMatch, skos:broadMatch, skos:narrowMatch, skos:relatedMatch

### skos-thes: - for the thesaurus / ontology  metadata

### skos-xl, xl:
- Still considered. Is used by YSO Ontology.

### xsd
xsd:integer, xsd:date

### voaf
- voaf:Vocabulary, voaf:VocabularySpace
- voaf:extends, voaf:propertyNumber, voaf:classNumber, voaf:specializes, voaf:similar, voaf:toDoList

### SEKO
Note!  will add to seko-metadata.ttl a new annotation property: ****seko:statusNote**** as a subProperty of skos:note .
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
****Value definitions****
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



