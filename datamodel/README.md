See documentation draft (work in progress) at [Datamodel document](./SEKO3-Datamodel.md)

# SEKO3 datamodel planning

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
@prefix skos-thes: <http://purl.org/iso25964/skos-thes#> .
@prefix voaf <http://purl.org/vocommons/voaf#> .
@prefix xl <http://www.w3.org/2008/05/skos-xl#> .
@prefix xsd <http://www.w3.org/2001/XMLSchema#> .
@prefix xml: <http://www.w3.org/XML/1998/namespace> .
#
@prefix bf: <http://id.loc.gov/ontologies/bibframe/> .
@prefix finna: <https://www.finna.fi/Record/> .
@prefix lcmpt: <http://id.loc.gov/authorities/performanceMediums/> .
@prefix hornbostelandsachs: <http://www.mimo-db.eu/HornbostelAndSachs/> .
@prefix mimo: <http://www.mimo-db.eu/InstrumentsKeywords/> .
@prefix mads: <http://www.loc.gov/mads/rdf/v1#> .
@prefix mstatus: <https://id.loc.gov/vocabulary/mstatus/> .
@prefix schema: <http://schema.org/>  .
@prefix seko: <http://urn.fi/urn:nbn:fi:au:seko:> .
@prefix seko-meta: <http://urn.fi/urn:nbn:fi:au:seko-meta:> .
@prefix seko-issues: <https://github.com/NatLibFi/SEKO/issues/> .
@prefix wd: <http://www.wikidata.org/entity/> .
@prefix yse-issue: <https://github.com/Finto-ehdotus/YSE/issues/> .
@prefix yso: <http://www.yso.fi/onto/yso/> .
```

## Classes and properties to be used
### owl:
- owl:Class, owl:ObjectProperty, owl:DatatypePropety, owl:AnnotationProperty, owl:TransitiveProperty, owl:Ontology, owl:Thing
owl:differentFrom, owl:imports, owl:inverseOf, owl:sameAs, owl:versionInfo, owl:versionIRI, 


### rdf: rdfs:
- rdfs:Class, rdf:Property, rdfs:Resource, rdfs:Label, rdfs:Literal, rdf:PlainLiteral
- rdf:type, rdf:langString, rdf:object, rdf:subject, rdf:language,
- rdfs:domain, rdfs:range, rdfs:subClassOf, rdfs:subPropertyOf,
- **rdfs:Datatype**  # local datatypes are defined and used for classification notations
- **rdfs:isDefinedBy** # used to point to a resource or vocabulary that defines the subject resource.
- **rdfs:comment** # used for giving a human readable label for a object URI
- **rdfs:seeAlso**  # Used for addtional external documentation describing the instrument or   
    other information useful in content description, e.g. link to an image of the instrument.
  - See [UsingSeeAlso](https://www.w3.org/wiki/UsingSeeAlso).

### dc: dct:
#### for the ConceptScheme
- dc:coverage, dc:creator, dc:format, dc:publisher, dc:title, dc:type
- dct:accessRights, dct:rights, dct:abstract, dct:accrualMethod, dct:accrualPeriodicity, dct:accrualPolicy, dct:audience, dct:available, dct:bibliographicCitation, dct:conformsTo, dct:contributor, dct:coverage, dct:creator, dct:language, dct:license, dct:mediator, dct:publisher, dct:subject, dct:title, dct:type

#### for a Concept
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
#### owl:Class:
- **skos:Concept**  #  Used for any instrument or ensemble element
- **skos:ConceptScheme**  #  Currently two schemes  seko: for the ontology and seko-meta: for the local class and property descriptions
- [skos:Collection](https://www.w3.org/TR/skos-reference/#Collection) # Used for grouping concepts, e.g. folk instruments, from different branches of the hierarchy.

#### Object Properties: 
- **skos:hasTopConcept**  # Used for the concept scheme.  Links to concepts that have no skos:broader properties
- **skos:member** #   Used for linking from a skos:Collection to its members
- **skos:inScheme**  # Used for skos:Concept to show which scheme (a vocabulary) it belongs to, a MANDATORY property for skos:Concept
- **skos:topConceptOf**  # Used for linking the top concept to the scheme it is a top concept of
- **skos:broader**  # Used for linking to hierarchically nearest broader concepts. There can be more than one.
- **skos:narrower** # Used for linking to the hierarchically nearest narrower conecpts, opposite to skos:broader
- **skos:related**  # Used for linking to a related skos:Cconcept WITHIN Seko but is not hierarchically broader or narrower
- skos:memberList  # currently not used

#### Datatype properties:
- **skos:notation**  #  Used for a alphanumeric label identifying e.g. a classification category. Use specified local datatypes for classifications.

#### Annotation properties:
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

#### Mapping properties:
- skos:mappingRelation, **skos:closeMatch**, **skos:exactMatch**, **skos:broadMatch**, **skos:narrowMatch**, **skos:relatedMatch**
  - Used for mapping Seko concepts to the same or similar concepts in external vocabularies

### skos-thes: - for the classification hierarchy and other grouping
This part is still under consideration.  It could be used for presenting the classification structure and the members of each group from the seko: ontology and possibly from the mimo: vocabulary.

If the group members follow the hierarchy, use ConceptGroup. and skos-thes:subGroup or skos-thes:superGroup for the group hierarchy. The Domain and Range for both is  skos-thes:ConceptGroup.
- [skos-thes:ConceptGroup](https://www.dublincore.org/specifications/skos-thes/ns/#ConceptGroup)
   - _Concept groups have several applications. One such application is illustrated by the EUROVOC and the UNESCO thesaurus. Both of these use a super structure of domain and micro-thesaurus. Both of these structuring elements can be modeled using ConceptGroup._
   - _A concept group is a group of concepts making up a subset of the thesaurus. Member concepts may be drawn from many different facets or hierarchies of the thesaurus. While almost any criterion may be used to select the members, this construct is commonly used to define a micro-thesaurus that will be used by a particular user group or domain._
   - _The skos:inScheme (http://www.w3.org/2004/02/skos/core#inScheme) property should be used to indicate the thesaurus to which an instance of skos:Collection applies (see ISO 25964: isPartOf)._
   - is disjoint with skos-thes:ThesaurusArray
- [skos-thes:superGroup](https://www.dublincore.org/specifications/skos-thes/ns/#superGroup)
   - All members of the (subject) group are members of the (object) superGroup
- [skos-thes:subGroup](http://purl.org/iso25964/skos-thes#subGroup)
   - All members of the (object) subGroup are members of the (subject) group.

If the group members are not hierarchically related to the members in the superordinate or subordinate groups, use Thesaurus Array classes and skos-thes:subordinateArray or skos-thes:superOrdinateArray. This could be used for non-classification groups based on the use (e.g. folk instrument), material (e.g. wood, metal, mixed), music genre (e.g. samba), spatial distribution, temoporal distribution (e.g. historical instruments) 
The 
- [skos-thes:ThesaurusArray](https://www.dublincore.org/specifications/skos-thes/ns/#ThesaurusArray)
    - _Definition: ISO ThesaurusArray.  An array is a group of sibling concepts
    - _Instances of ThesaurusArray can be mapped to instances of skos:OrderedCollection (a subclass of skos:Collection) if and only if the array needs to be an ordered array (in the ISO-25964 model the value of its Boolean attribute "ordered" is true)._
    - _It is advised to use the skos:inScheme (http://www.w3.org/2004/02/skos/core#inScheme) property on such a skos:Collection to relate it to its Thesaurus (see ISO 25964: isPartOf)._
    - subClass of skos:Collection. 
- [skos-thes:suborOdinateArray](https://www.dublincore.org/specifications/skos-thes/ns/#suborOdinateArray)
    - _Explicitly links a (superordinate) concept to one or more subordinate arrays. Each array may either be composed of narrower concepts of the superordinate concept (in which case there may be an associated node label with a characteristic of division) or by concepts that need not be narrower concepts of the superordinate concept (in which case a node label may provide a facet name)._
    - _In other words, though each array only contains sibling concepts, no hierarchical relation may be automatically derived between a concept and the concepts in any of its subordinate arrays. The hierarchical relationship between these concepts has to be asserted explicitly._
    - Domain is skos:Concept, Range is skos-thes:ThesaurusArray, inverseOf skos-thes:superOrdinate
- [skos-thes:superOrdinate](https://www.dublincore.org/specifications/skos-thes/ns/#superOrdinate)
    - _The (subject) array organizes a set of sibling concepts under the (object) concept._
    - Domain is skos-thes:ThesaurusArray, Range is skos:Concept, is inverse Of skos-thes:subOrdinateArray

### skos-xl, xl:
- Still considered. Is used by YSO Ontology.

### xsd
xsd:integer, xsd:date, xsd:dateTime

### voaf
- voaf:Vocabulary, voaf:VocabularySpace
- voaf:extends, voaf:propertyNumber, voaf:classNumber, voaf:specializes, voaf:similar, voaf:toDoList

## SEKO
Note!  will add to seko-metadata.ttl a new annotation property:   
****seko:statusNote**** as a subProperty of skos:note .

Planned prefix is **seko-meta:**

### Possible class definitions 
```
seko:MediumOfPerformance a owl:Class ;  
    rdfs:subClassOf skos:Concept ;   
    skos:exactMatch <http://id.loc.gov/ontologies/bibframe/MediumOfPerformance> ;    
    skos:prefLabel "Esiintymiskokoonpano"@fi , "Medium of performance"@en ;
    rdfs:label "Medium of performance"@en ;  
    skos:topConceptOf seko: ;
    skos:definition "An individual instrument, voice, ensemble, or instrumental group (Bibframe)"@en ;  
```

```
seko:MusicInstrument a owl:Class ; rdfs:subClassOf skos:Concept ;  
   skos:exactMatch <http://id.loc.gov/ontologies/bibframe/MusicInstrument> ;   
   skos:prefLabel "Soitin"@fi, "Music instrument"@en ;
   rdfs:label "Music instrument"@en ;
   skos:broader seko:MediumOfPerformance ;
   skos:definition "Instrument for which a musical work is appropriate (Bibframe)"@en ;
   skos:exactMatch yso:p7110 .  # "soitin"
```

```
seko:MusicEnsemble rdfs:subClassOf skos:Concept ;   
   skos:prefLabel "Ensemble"@fi, "Music ensemble"@en ;  
   rdfs:label "Music ensemble"@en ;
   skos:exactMatch <http://id.loc.gov/ontologies/bibframe/MusicEnsemble> ;   
   skos:broader seko:MediumOfPerformance ;
   skos:definition "Ensemble for which a musical work is appropriate (Bibframe)"@en ;  
   skos:closeMatch  <https://schema.org/MusicGroup> . 
```


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

## Notation of Classifications 
Two rdfs:Datatype entities were added to handle the notations: 
- seko:HSNotation
- seko:YKLNotation 
Examples and discussion How they would be used are in the classification section.

## Concept minimum content
For any concept the **minimum** set of properties is:
- rdfs:type
- skos:prefLabel
- dct:identifier
- skos:broader (or skos:topConeptOf)
- skos:exactMatch 

## Example of a fuller concept data
```
to be added
```

## Value vocabularies
See more in the folder [vocabulary](../vocabulary/README.md)
- Some vocabularies would be used locally by adding Finnish and Swedish labels to more general values
- these concepts could be copied into a local vocabulary aand mapped with skos:exactMatch to the original vocabulary
- Some external value vocabularies could be used directly (Metadata Thesaurus, Spatial, Termporal, etc.)

----
`TBC`



