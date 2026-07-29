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
