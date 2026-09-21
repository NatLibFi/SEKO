# Editorial process on FMPO concepts
As of Septermber 2026 
Editorial work is going on through Github issues and the results are updated to the Google sheet (138 open issues)
- 1174 concepts are waiting to be checked.
- 83 concepts are missing wikidata mapping
- About 50 concepts are missing a Swedish prefLabel
- 27 Seko concpets are marked for deprecation mostly due to splits and merges of concepts.

## Editorial tasks during concept checking
- **skos:prefLabel** in three languages: Finnish, Swedish, English
- **skos:altLabel** are checked to belong to this instrument, their language tags are added
     - checking altLabels and mappings may lead to **merge** or **split** processes
- **Mappings** are checked / added for corresponding concepts in Seko, YSO, KOKO, YKL, Wikidata, LCMPT, MIMO.  H-S classification. 
- **skos:hiddenLabel** added for prefLabels with diacritical characters, or plural vs single label form
- Seko **skos:note** property values:
     - The text may be edited and then translated to Swedish and English
     - **spatial** and **temporal** information checked from skos:note and entered as linked data properties,   (**dct:spatial** YSO Places, **dct:temporal** YSO Time)
     - Possible other information as linked data as well (**material**, **genre**, **user**)
- **Group information**
     - the appropriate instrument groups may be added to the dataset if needed (e.g. Finnish-Karelian traditional instruments, folk instruments, shepards' instruments, etc.)
     - These groups are of type skos-thes:ThesaurusArray (groups of sibling concepts without hieararchical relationships)
     - the membership information is added to the group entity with **skos:member**
- Deprecated concepts should have a **dct:isReplacedBy**
- Links to near-by or similar instruments may be added  (**skos:related**) 
- references to sources of metadata are added (**dct:source**)
- links to additional descriptive information may be added  (**rdfs:seeAlso**)
- **Annotations** may be added (skos:definition, skos:note, skos:changeNote, skos:historyNote, skos:editorialNote)
- Add skos:inScheme "fmpo:"
- add the appropriate type for each concept  either fmpo:Instrument or fmpo:Ensemble

## Minimum content for a FMPO concept
- prefLabel (3)
- skos:broader  (excpet for the two topCOncept)
- skos:note
- mapping to Seko (except for the added concepts)
- mapping to Wikidata (mandatory, add new item  if not existing)
- dct:modified

## Preferred content
- altLabel with language tag
- dct:spatial -  origin or usage region or country
- mappings to YSO, MIMO, LCMPT, H-S classification
- H-S class notation as a string
- skos:defnition -  should add the source, too
- dct:created 
- skos:changeNote  - explain notable changes, mark the date

## Extra content
- skos:related - links to similar concepts within fmpo:
- skos:example  "string"
- rdfs:seeAlso - links to external descriptions and examples of the instrument
- IF owl:depreacated true THEN dct:isReplacedBy
- skos:historyNote - previous content of the concept
- skos:editorialNote - reminders and other maintenance information
- mappings to other schemes: MARC21 instrument codes, Getty AAT, discogs, musicbrainz
