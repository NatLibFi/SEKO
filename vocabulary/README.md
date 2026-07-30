# Vocabularies for additional metadata
For some additional properties there are no simple lists available in other sources.

## Example "material"

Property could be either based on wikidata, rdau: or schema:

AI-generated example of a value vocabulary for "material" of musical instruments.
[material.ttl](./material.ttl)

### optional additional properties for the datamodel
|property |object|
|-|-|
|material|animal horn|
| [schema:material](https://schema.org/material) |[wd:Q82025](http://www.wikidata.org/entity/Q82025) "sarvi"|
|[wdp:P186](http://www.wikidata.org/entity/P186)|[wd:Q82025](http://www.wikidata.org/entity/Q82025)|
|[rdau:P60995](http://rdaregistry.info/Elements/u/P60995)|<http://www.yso.fi/onto/tao/p621> ; # sarvi (materiaalit) - monolingual |

Source for the concepts could be Getty AAT. It does have property [aat2502_material_for](https://vocab.getty.edu/ontology#anchor-2111703447)
- ttp://vocab.getty.edu/ontology#aat2502_material_for  inverse of:
    - http://vocab.getty.edu/ontology#aat2501_made_of-require
    - things - [are] made of/require - material.
    - Example: obsidian mirrors are made of/require obsidian; ivories (sculptures) are made of/require ivory
    - This property is defined by [Art and Architecture Thesaurus](https://vocab.getty.edu/ontology#anchor-1767998373)
    - SPARQL endpoint https://vocab.getty.edu/
 
 Pick appropriate materials from here if they are not specifically grouped as materials for music instruments
    - https://www.getty.edu/vow/AATHierarchy?find=material&logic=AND&note=&page=1&subjectid=300010358
    - https://www.getty.edu/vow/AATHierarchy?find=instrument&logic=AND&note=&page=1&subjectid=300387677


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

#### second option: MARC21 

A second option could be to use the MARC [Status codes](http://id.loc.gov/vocabulary/mstatus)  
Codes and term sources to indicate the status of a resource. 
Here is a selection of the list which could be used here:
- mstatus:[new](http://id.loc.gov/vocabulary/mstatus/n)
        - Resource is newly-created  (note: e.g. issued before approving, a test case)
- mstatus:[incomplete](http://id.loc.gov/vocabulary/mstatus/incmp)
        - Information contained in the resource is incomplete
- mstatus:[partial](http://id.loc.gov/vocabulary/mstatus/part)
        - Information contained in the resource is partially or selectively included (note: e.g. core fields are missing)- mstatus:[current](http://id.loc.gov/vocabulary/mstatus/current)
        - Resource is currently published or the frequency status is current (note: correct and active)
- mstatus:[c](http://id.loc.gov/vocabulary/mstatus/c) (changed)
        - Resource has been edited  (note: express time with dct:modified)
- mstatus:[incorrect](http://id.loc.gov/vocabulary/mstatus/incorrect)
        - (note: a rare occasion, e.g. if a double entry is found)
- mstatus:[s](http://id.loc.gov/vocabulary/mstatus/s) (suppressed)
        - Resource is suppressed from public display
        - (Note: in the masterdata but not published, this shoud not be linked to by any other entity)
- mstatus:[cancinv](http://id.loc.gov/vocabulary/mstatus/cancinv)  (canceled or invalid)
        - Identifier that has been cancelled or is not valid for the resource being described
        - owl:deprecated TRUE

## External value vocabularies per property

### dct:spatial
- <https://www.yso.fi/onto/yso/p94426> (YSO-places - Finland) **Use primarily**
- <http://www.wikidata.org/entity/Q33> (Wikidata - Finland)
- <https://www.geonames.org/660013/> (Geonames.org - Finland)

### dct:temporal
For referring to **time period** use `dct:temporal`  object primarily a YSO time or wikidata concept.
For referring to **music of era** use `skos:relatedMatch` 
- EDTF Specification https://www.loc.gov/standards/datetime/

The relationship to the music style could be eithe dct:relation or <https://www.wikidata.org/wiki/Property:P366> "has use" ("used in") | "käyttö" ("käytetään")

#### The Eras used by Grove Music Online:
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

#### Music styles for the eras 
See also [https://en.wikipedia.org/wiki/Dates_of_classical_music_eras](https://en.wikipedia.org/wiki/Dates_of_classical_music_eras)

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

**Note!** This applies only to the [Western classical music](https://en.wikipedia.org/wiki/Classical_music). Asian, African and Latin American cultures have different eras. E.g. 
- wd:Q59158 dhrupad | ancient genre of clacssical Indian music
- wd:Q70076 tappa | Hindustan classical music genre (singing)




## Additional possible properties for consideration

  # tätä  voidaan käyttää soittimien tiedoissa, 
  # kun skos:notation ominaisutta käytetään luokkia vastaaville ryhmille  

### Classification

<http://www.wikidata.org/entity/P1762> a owl:DatatypeProperty ;  
    rdfs:label "Hornbostel-Sachs-luokka"@fi, "Hornbostel-Sachs class"@en ;  
    rdfs:domain seko:Instrument ;  
    rdfs:range rdfs:Literal ;  
    skos:scopeNote "Hornbostel-Sachs-luokitusnumero akustisen ja rakenteellisen analyysin tueksi (MIMO-yhteensopivuus)."@fi ;  
    dc:source <https://wikidata.org> .  

### Material
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

#### Manufacturer (dct:Agent, foaf:Agent, schema:Agent)

<https://schema.org/manufacturer> a owl:ObjectProperty ;  
    rdfs:label "Valmistaja"@fi ;  
    rdfs:comment "Henkilö tai organisaatio, joka on rakentanut tai valmistanut soittimen."@fi ;  
    rdfs:domain seko:Instrument ;  
    rdfs:range dct:Agent .
