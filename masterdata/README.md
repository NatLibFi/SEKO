The masterdata file has been in a google sheet hosted by the editor of the dataset
WHen the major editorial work has been done, the data will be converted to RDF

## Masterdata table structure 
There are two types of rows 
- Type 1: concept rows with all property values. Mandatory `A,D,E,F,M,AE`
- Type 2: rows for altLabel and hiddenLabel values and language tags. Values in column `A,G,H` or `A,I,J` only

Formatting
- Multiple values of plain literal strings are separated with character `|`.
- Language tagged literals are entered with parentheses and the tag and separated with a comma `,`.
    - E.g. `finnish text"@fi, "swedish text"@sv`
- References to Seko concepts are entered in the format `seko:nnnnn`.

## Column labels and descriptions
- list updated as of v2026-08-31 - added column A from fmpo id.
```
A fmpo                   (prefix:sekoID - - mandatory value on each line)
B skos:exactMatch seko   (Concept ID as full URL - only on first concept line)
C owl:deprecated         (only value is TRUE, entered if the concept is deprecated) 
D skos:prefLabel_fi      (rdfs:Literal - mandatory value)
E skos:prefLabel_sv      (rdfs:Literal - mandatory value)
F skos:prefLabel_en      (rdfs:Literal - mandatory value) 
G skos:altLabel          (rdfs:Literal)
H alt_lang               (rdfs:Literal, 2-3 character language code)  
I skos:hiddenLabel       (rdfs:Literal) 
J hidden_lang            (rdfs:Literal, 2-3 character language code)
K spatial-uri            (object value for dct:spatial property)
L dct:spatial            (label for the object, not needed in RDF)
M skos:topConceptOf      (only one topConcept now (medium of performance) -- NEW
N skos:broader           (Full URI value, several are separated with | - mandatory value)
0 skos:broader_Label     (label for the broader concept, not needed in RDF)
P editorial_issue_URL    (URL to Github issues concerning the concept)
Q YSO-ID                 (skos:exactMatch object value, URL to YSO-concept)
R wikidata-id            (skos:exactMatch, obect value, URL to Wikidata-item)
S skos:editorialNote     (rdfs:Literal)
T H&S_notation           (string rdfs:Literal, label for H-S classification link)
U H&S-ID                 (URL for skos:related object)
V MIMO-ID                (skos:exactMatch object value, URL to dbpedia)
V dbpedia                (skos:closeMatch object value, URL to dbpedia)
X SEKO-LCMPT-mapping     (property for the LCMPT relationship as a string)
Y LCMPT-ID               (URL of LCMPT concept, rdfs:Literal)
Z rdfs:seeAlso           (URL of rfs:seeAlso object value, links to documentation, etc.)
AA dct:isReplacedBy       (replancing concept within the vocabulary, format seko:nnnnn)
AB skos:related           (related concept within the vocabulary, format seko:nnnnn)
AC skos:definition       (comma spearated language-tagged strings, rdf:langString)
AD skos:scopeNote        (comma spearated language-tagged strings, rdf:langString)
AE skos:changeNote       (rdfs:Literal)
AF skos:historyNote      (previous history of the concept, e.g. in earlier versions) - NEW
AG skos:modified         (last modification date,  xsd:date)
AH seko:statusNote       (string label or URI, to the selected controlled vocabulary)
AI skos:noteSeko1        (description in the finto.fi seko monolingual Finnish version) - NEW
AJ iconclass id          (new)
```

Expected data structure after conversion in Turtle format
Values from the table are represented with the column label.
```
A   a skos:Concept      ;
    skos:exactMatch B   ;      # mapping to Seko concept
#   owl:deprecated TRUE   ;    # for decprecated concepts only
#   dct:isReplacedBy    Y ;    # for decprecated concepts only
    skos:prefLabel     "C"@fi, 
                       "D"@sv, 
                       "E"@en ;
    dct:spatial          J ;    # URL, link to YSO-paikat
    skos:broader         L ;    # link to seko concept as seko:nnnnn
    skos:related         N ;    # links to github issues
    skos:exactMatch O, P, T ;  # links to YSO, Wikidata, MIMO
    V                    W ;    # predicate + object - mapping to LCMPT
    skos:related         Z ;    # related concept within the vocabulary
    dct:subject [ a skos:Concept ; skos:notation "S" ] ; # Using a blank node
    skos:broadMatch     T ;    # Hornbostel-Sachs mapping as URL 
    skos:closeMatch     U ;    # link to corresponding concept in dbpedia 
    rdfs:seeAlso        X ;    # link to documentation etc.
    skos:definition    AA ;    # comma spearated language-tagged strings
    skos:scopeNote     AB ;    # comma spearated language-tagged strings
    skos:changeNote    AC ;    # rdfs:Literal  (public note)
    skos:editorialNote  Q ;    # rdfs:Literal
    skos:historyNote   AE ;    # previous changes, first issue etc.
    skos:modified      AD ;    # last modification date,  xsd:date
    skos:statusNote    AE ;    # value from controlled vocabulary?
    skos:relatedMatch AJ .     # mappings to inconclass instruments
```

skos:altLabel  and skos:hiddenLabel could be loaded as triplets directly
```
`A` skos:altLabel     "`F`"@`E` .
`A` skos:hiddenLabel  "`H`"@`J` .
```
> these need to be modelled carefully H-S notation, H-S link thinking how they are stored:
> The content editor will add only the notation (dropdown?) The link should appear automatically
>  S ;  the HS class code  
>  T ;  link to the local clasas definition with local labels 
