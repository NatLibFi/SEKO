## SEKO3 project log - activity notes  
[Go back to homepage](./README.md#previous) | Jump to <a href="./activitynotes.md#202607">2026-07</a>
### 2023-01
- First issuse created in January - By September issue nr. 49 was created.

### 2023-05 
- Note! There are several possibly problematic concepts due to overlapping distribution of the same or similar instruments over several cultural and linguistic regions. Some concepts may need to be split up and some others should be joined to a single concept. These will be brought up as issues where they can be then discussed. See the list at Issue(https://github.com/NatLibFi/SEKO/issues)

### 2024-11
- created five new issues
- worked on mapping MARC field 048 - SEKO - LCMPT

### 2025
- no activity

### <a id="2026-06">2026-06</a>
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


