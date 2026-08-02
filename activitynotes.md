## SEKO3 project log - activity notes  
[Go back to homepage](./README.md#previous)   
| Jump to <a href="./activitynotes.md#202607">2026-07</a> | <a href="./activitynotes.md#202608">2026-08</a>

### 2023-01
- First issuse created in January - By September issue nr. 49 was created.

### 2023-05 
- Note! There are several possibly problematic concepts due to overlapping distribution of the same or similar instruments over several cultural and linguistic regions. Some concepts may need to be split up and some others should be joined to a single concept. These will be brought up as issues where they can be then discussed. See the list at Issue(https://github.com/NatLibFi/SEKO/issues)

### 2024-11
- created five new issues
- worked on mapping MARC field 048 - SEKO - LCMPT

### 2025
- no activity

### <a id="202606">2026-06</a>
**Week 27**
- As of June 2026 the list of instrument names in Swedish is lacking 58 labels. 57 English labels are missing.  MIMO may have some, but additional labels are needed.
- After handling all the open  issues here whe should have labels in 3 languages with a Wikidata-mapping for all current and some newly added items.
- During the editing some items will be DEPRECATED due to MERGE or other reasons. See the lists of planned <a href="./doc/deprecated-concepts.md">deprecations</a> and <a href="./doc/new-concepts.md">addtions</a>.

### <a id="202607">2026-07</a>

**Week 28**
- Started adding the rest of the issues for concepts needing actions in the Masterdata table.
- All planned issues on problematic instruments or those without mappings have been created.  On 2026-07-05 there are 141 "open" issues and 30 "solved". The unfinished masterdata backup was uploaded as a CSV file to the repository. Created a description of the columns in the masterata table (masterdata.md) and added a description of the data model in  the wiki section.
- The [MIMO vocabulary](https://vocabulary.mimo-international.com/en/about) was contacted concerning data download and Finnish labels. 
- **Sources for labels** The list was updated with additional sources and moved to the Seko Wiki (see the link above) - See also the list of printed sources used in the original Seko vocabulary. <a target="_self" href="https://github.com/NatLibFi/SEKO/wiki/K%C3%A4ytt%C3%B6ohjeet-Aidatrumpetista-zimbalomiin--sanastolle#l%C3%A4hdeluettelo">Lähdeluettelo</a>
- The Finnish Expert Group on Music Metadata **MUUSA**  decisions on SEKO concepts during 2021-01/2026-06 have been copied from their [wiki list](https://www.kiwi.fi/spaces/muusa/pages/106333360/Valmiit) to here as issues and marked with the label [MUUSA](https://github.com/NatLibFi/SEKO/issues?q=is%3Aissue%20label%3AMUUSA).
   - **Please note** that their decisions on SEKO concepts before 2019 are documented in the SEKO wiki on page <a href="https://github.com/NatLibFi/SEKO/wiki/Timeline-of-decisions-and-changes-in-the-SEKO-vocabulary-and-its-predecessor-Aidatrumpetista-zimbalomiin">Timeline of decisions and changes in the SEKO vocabulary and its predecessor Aidatrumpetista zimbalomiin</a>.
   - Both of these are now stored as `skos:historyNote` values in a separate ttl-file in the masterdata -folder. 
- Imported the predecessor "Soitinnimien ohjeluettelo" laast version (Oct, 2017) from Web Archive. Will post it in the Wiki. Downloaded also the first online version of 2002 from Web Archive. 


**Week 29**
- Added documentation in the Wiki section about the planned new Data Model of SEKO3, SPARQL searching in Finto (and later Wikidata), list of concepts set for deprecation, plans for properties, added more items to the list of information source resources,  etc.
- Improved usability of the repository by creating subdirectories "doc", "datamodel" and "masterdata". Moved the datamodel documentation from wiki.
- started documenting SPARQL queries in th Wiki section. E.g. all skos:note field values of in Seko at finto.fi  into a table, etc.
- The issues in which the instruments were missing a Swedish prefLabel were labelled `svenskt namn saknas` and those missing a mapping to `wikidata`.
- Wrote a short intermediary status report which was sent to the Muusa group.
- Createad an AI-generated status report of the masterdata-table (with Claude Sonnet 5) - still adusting. Visible in the Wiki section Väliraportti as a PDF. Created also Claude skills for retrieving instrument information from various sources and  for instrument comparisons.
- Created an issue label `AI-generated` for specifying the issues which have comments that include AI-generated content.
- Created a `seko-metadata.ttl` in the datamodel directory for the new ontology schema metadata.  Created issue #185  about the description of the ontology in Swedish and English and also a `Milestone` for issues that are related to the whole ontology.
- Took the current skos:note values (descriptions) via the finto.fi API and added them into the masterdata-table as a separate column in preparation for updates, and translations as well as for checking the spatial and temporal information.

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
- Considered properties for "material" of instruments. Searched for vucabularies. Looked at the Musketti instructions and the Europeana Data Model and instrument metadata there.
    - Created a folder "vocabulary" for a potential solution for any required lists of items (such as status codes and imstrument materials).  Created a demo vocabulary of "materials" with a AI-assistant based on data from Seko definitions.
    - There might be a potential to add these into Metadata vocabulary for a more general use?
- Tested using AI for finding language tags for undefined altLabels for an Indian instrument. Worked well and fast (labels were in hi,or,ta,gu,ml,mr,pa,sa). [#192](https://github.com/NatLibFi/SEKO/issues/192).  Stored the rules in the `doc/methods` -folder.   
- Worked on a group of several issues dealing with related animal horn instruments around the Baltic. [#118](https://github.com/NatLibFi/SEKO/issues/118)
- Restructured the datamodel examples for the options to present class notations for the Hornbostel-Sachs and YKL classifications.  Looked at various instrument classifications and their labeling.
- Mapped some Swedish labels to be used in the datamodel (`doc/skos-vocabulary.md`) in case not available in Skosmos.

### <a id="202608">2026-08</a> AUGUST

**Week 32**

