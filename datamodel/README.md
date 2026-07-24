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
@prefix mstatus: <https://id.loc.gov/vocabulary/mstatus/> .
@prefix seko: <http://urn.fi/urn:nbn:fi:au:seko:> .
@prefix seko-meta: <http://urn.fi/urn:nbn:fi:au:seko-meta:> .
@prefix seko-issues: <https://github.com/NatLibFi/SEKO/issues/> .
@prefix wd: <http://www.wikidata.org/entity/> .
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
- **skos:notation**  #  Used for a alphanumeric label identifying e.g. a classification category. Not the same as identifier.

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

### skos-thes: - for the thesaurus / ontology  metadata
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
## Concept minimum content
For any concept the **minimum** set of properties is:
- rdfs:type
- skos:prefLabel
- dct:identifier
- skos:broader (or skos:topConeptOf)
- skos:exactMatch 

## Example of a fuller concept data


## Value vocabularies used

### seko-meta:statusNote
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
Codes and term sources to indicate the status of a resource. 
Here is a selection of the list which could be used here:
- [canceled or invalid](http://id.loc.gov/vocabulary/mstatus/cancinv)
        - Identifier that has been cancelled or is not valid for the resource being described
        - owl:deprecated TRUE
- [changed](http://id.loc.gov/vocabulary/mstatus/c)
        - Resource has been edited  (note: express time with dct:modified)
- [current](http://id.loc.gov/vocabulary/mstatus/current)
        - Resource is currently published or the frequency status is current (note: correct and active)
- [incomplete](http://id.loc.gov/vocabulary/mstatus/incmp)
        - Information contained in the resource is incomplete
- [incorrect](http://id.loc.gov/vocabulary/mstatus/incorrect)
        - (note: a rare occasion, e.g. if a double entry is found)
- [new](http://id.loc.gov/vocabulary/mstatus/n)
        - Resource is newly-created  (note: e.g. issued before approving, a test case)
- [partial](http://id.loc.gov/vocabulary/mstatus/part)
        - Information contained in the resource is partially or selectively included (note: e.g. core fields are missing)
- [suppressed](http://id.loc.gov/vocabulary/mstatus/s)
        - Resource is suppressed from public display
        - (Note: in the masterdata but not published, this shoud not be linked to by any other entity)

### dct:spatial
- YSO-places  Use primarily  **https://www.yso.fi/onto/yso/**p94426 (Finland)
- Wikidata - **http://www.wikidata.org/entity/**Q33 (Finland)
- Geonames.org - **https://www.geonames.org/**660013/ (Finland)

### dct:temporal
For referring to **time period** use `dct:temporal`  object primarily a YSO time or wikidata concept.
For referring to **music of era** use `skos:relatedMatch` 
- EDTF Specification https://www.loc.gov/standards/datetime/
- 
The relationship to the music style could be eithe dct:relation or <https://www.wikidata.org/wiki/Property:P366> "has use" ("used in") | "käyttö" ("käytetään")

These are the Eras used by Grove Music Online:
- GMO: Pre- and Early Medieval (before 800)
    - yso:p4622 **esihistoria** | prehistory
    - wd:Q41493 Anciet history (before Middle Ages) | - (before 500)  **(fi: -476)**
- GMO: Medieval (800-1400) - "0800/1400"    **(fi: 476-1400)**
    - yso:p2559 **keskiaika** | Middle Ages
- GMO: 15th century/Early Renaissance (1400-1500)
    - yso:p4978 **varhaisrenessanssi** Early Renaissance
- GMO: 16th century/High Renaissance (1500-1600)
    - yso:p16253 **täysrenessanssi** | High Renaissance    **(fi: 1400-1600)**
- GMO: 17th century/Early to mid-Baroque (1600-1700)
    - wd:Q37853 Baroque | barokki (1600-1750)
    - yso:p15757 **barokki** | baroque  **(fi: 1600-1750)**
- GMO: Early 18th century/Late Baroque (1700-1750)
    - wd:Q64334168 Late Baroque | myöhäisbarokki (1675-1715)
    - wd:Q1141686 Galante music | galantti msuiikki **(fi: 1720-1775)**
- GMO: Late 18th century/Classical (1750-1800)
    - yso:p10167 **klassisismi** | classicism  **(fi: 1770-1830)**
    - wd:Q14378 "neo-classicism | uusklassismi (1760-1830)
- GMO: 19th century/Romantic (1800-1900)
    - yso:p12824 **romantiikka** | Romantic Era  **(fi: 1815-1910)**
    - yso:p25635 **myöhäisromantiikka** | late romanticism
    - wd:Q1125039 Post-romanticism | jälkiromantiikka (1815-1848)
- GMO: 20th century (1900-2000) (1900-1999)
    - yso:p5001 modernismi | modernism 
    -  wd:Q2426218 **modernism** | modernismi
- GMO: 21st century (2000-present) (2000-)
    - wd:Q6939 21st century | 2000-luku
 
Music styles for the eras. See also [https://en.wikipedia.org/wiki/Dates_of_classical_music_eras](https://en.wikipedia.org/wiki/Dates_of_classical_music_eras)
- wd:Q761684 prehistoric music | - (preliterate cultures, primitive music)
- wd:Q18846 ancient music | antiikin musiikki
- wd:Q163775 medieval music | keskiajan msiikki (400-1400)
- wd:Q201405 renaissance music | renessanssimusiikki (1400-1600) 
- wd:Q2884829 early baroque music  (1600-)
- wd:Q8361 baroque music (1500-1750)
- wd:Q97359235 Late Baroque (music genre)
- wd:Q17723 Classical period | klassismin musiikki (1730-1820)
- wd:Q207591 Romantic music | romantiikan musiikki (1800-1900)
- wdQ65937946 modern classical music | taidemusiikki (1900- )
- wd:Q2426218 modernist music | modernismi (1900-1950)
- wd:Q612024 contemprorary classical | nykytaidemusiikki (1945- )
- wd:Q1338153 20th-century classical music | 1900-luvun taidemusiikki
- wd:Q4631020 21st-century classical music | 2000-luvun taidemusiikki

Note! This applies only to the [Western classical music](https://en.wikipedia.org/wiki/Classical_music). Asian, African and Latin American cultures have different eras. E.g. 
- wd:Q59158 dhrupad | ancient genre of clacssical Indian music
- wd:Q70076 tappa | Hindustan classical music genre (singing)


## Additional possible properties for consideration
**seko:Instrument** a skos:Concept ; skos:exactMatch <http://id.loc.gov/ontologies/bibframe/MusicInstrument> ; skos:exactMatvh yso:p7110 .
**seko:Ensemble** a skos:Concept ; skos:exactMatch <http://id.loc.gov/ontologies/bibframe/MusicEnsemble> ; skos:closeMatch  <https://schema.org/MusicGroup>. 

 # tätä  voidaan käyttää soittimien tiedoissa, kun skos:notation ominaisutta käytetään luokkia vastaaville ryhmille  
<http://www.wikidata.org/entity/P1762> a owl:DatatypeProperty ;  
    rdfs:label "Hornbostel-Sachs-luokka"@fi, "Hornbostel-Sachs class"@en ;  
    rdfs:domain seko:Instrument ;  
    rdfs:range rdfs:Literal ;  
    skos:scopeNote "Hornbostel-Sachs-luokitusnumero akustisen ja rakenteellisen analyysin tueksi (MIMO-yhteensopivuus)."@fi ;  
    dc:source <https://wikidata.org> .  

<https://schema.org/material> a owl:ObjectProperty ;  
    rdfs:label "Materiaali"@fi, "Material"@en ;  
    rdfs:domain seko:Instrument ;  
    rdfs:range rdfs:Resource ;  # Use  MTS mts:m654 members OR YSO concepts  OR Wikidata entities / groups 
    skos:scopeNote "Soittimen tyypillinen valmistusmateriaali (esim. puu, messinki). Hyödyllinen museoluetteloinnissa."@fi ;  
    dc:source <https://schema.org> .


<http://www.wikidata.org/entity/P186>  a owl:ObjectProperty ;  
    rdfs:label "Valmistusmateriaali (Wikidata)"@fi, "Material used (Wikidata)"@en ;  
    rdfs:domain seko:Instrument ;  
    rdfs:range rdfs:Resource ;  
    skos:scopeNote "Wikidata-pohjainen linkitys valmistusmateriaaliin monikielisyyden ja linkitetyn datan yhteensopivuuden tueksi."@fi ;  
    dc:source <https://wikidata.org> .  


<https://schema.org/manufacturer> a owl:ObjectProperty ;  
    rdfs:label "Valmistaja"@fi ;  
    rdfs:comment "Henkilö tai organisaatio, joka on rakentanut tai valmistanut soittimen."@fi ;  
    rdfs:domain seko:Instrument ;  
    rdfs:range dcterms:Agent .


 

----
`TBC`



