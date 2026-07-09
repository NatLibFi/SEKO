## Masterdata structure 
There are two types of rows 
- Type 1: concept rows with all property values. Mandatory `A,C,D,E,L,AD`
- Type 2: rows for altLabel and hiddenLabel values and language tags. Values in column `A,F,G` or `A,H,I` only

Formatting
- Multiple values of plain literal strings are separated with character `|`.
- Language tagged literals are entered with parentheses and the tag and separated with a comma `,`.
    - E.g. `finnish text"@fi, "swedish text"@sv`
- References to Seko concepts are entered in the format `seko:nnnnn`.

## Column labels and descriptions
```
A seko                   (Concept ID as full URL - mandatory value)
B owl:deprecated         (only value is TRUE, entered if the concept is deprecated) 
C skos:prefLabel_fi      (rdfs:Literal - mandatory value)
D skos:prefLabel_sv      (rdfs:Literal - mandatory value)
E skos:prefLabel_en      (rdfs:Literal - mandatory value) 
F skos:altLabel          (rdfs:Literal)
G alt_lang               (rdfs:Literal, 2-3 character language code)  
H skos:hiddenLabel       (rdfs:Literal) 
I hidden_lang            (rdfs:Literal, 2-3 character language code)
J spatial-uri            (object value for dct:spatial property)
K dct:spatial            (label for the object, not needed in RDF)
L skos:broader           (Full URI value, several are separated with | - mandatory value)
M skos:broader_Label     (label for the broader concept, not needed in RDF)
N editorial_issue_URL    (URL to Github issues concerning the concept)
O YSO-ID                 (skos:exactMatch object value, URL to YSO-concept)
P wikidata-id            (skos:exactMatch, obect value, URL to Wikidata-item)
Q skos:editorialNote     (rdfs:Literal)
R H&S_notation           (string rdfs:Literal, label for H-S classification link)
S H&S-ID                 (URL for skos:related object)
T MIMO-ID                (skos:exactMatch object value, URL to dbpedia)
U dbpedia                (skos:closeMatch object value, URL to dbpedia)
V SEKO-LCMPT-mapping     (property for the LCMPT relationship as a string)
W LCMPT-ID               (URL of LCMPT concept, rdfs:Literal)
X rdfs:seeAlso           (URL of rfs:seeAlso object value, links to documentation, etc.)
Y dct:isReplacedBy       (replancing concept within the vocabulary, format seko:nnnnn)
Z skos:related           (related concept within the vocabulary, format seko:nnnnn)
AA skos:definition       (comma spearated language-tagged strings, rdf:langString)
AB skos:scopeNote        (comma spearated language-tagged strings, rdf:langString)
AC skos:changeNote       (rdfs:Literal)
AD skos:modified         (last modification date,  xsd:date)
AE status                (string label or URI, to the selected controlled vocabulary)
```

Expected data structure after conversion in Turtle format
Values from the table are represented with the column label.
```
A   a skos:Concept      ;
#   owl:deprecated TRUE   ;    # for decprecated concepts only
#   dct:isReplacedBy  `Y` ;    # for decprecated concepts only
    skos:prefLabel "C"@fi, 
                   "D"@sv, 
                   "E"@en ;
    dct:spatial         J ;    # URL, link to YSO-paikat
    skos:broader        L ;    # link to seko concept as seko:nnnnn
    skos:related        N ;    # links to github issues
    skos:exactMatch O, P, T ;  # links to YSO, Wikidata, MIMO
    V                   W ;    # predicate + object - mapping to LCMPT
    skos:related        Z ;    # related concept within the vocabulary
    skos:broadMatch     S ;    # Hornbostel-Sachs mapping as URL 
    skos:closeMatch     U ;    # link to corresponding concept in dbpedia 
    rdfs:seeAlso        X ;    # link to documentation etc.
    skos:definition    AA ;    # comma spearated language-tagged strings
    skos:scopeNote     AB ;    # comma spearated language-tagged strings
    skos:changeNote    AC ;    # rdfs:Literal  (public note)
    skos:editorialNote  Q ;    # rdfs:Literal
    skos:modified      AD ;    # last modification date,  xsd:date
    status             AE .    # value from controlled vocabulary?
```

skos:altLabel  and skos:hiddenLabel could be loaded as triplets directly
```
`A` skos:altLabel     "`F`"@`E` .
`A` skos:hiddenLabel  "`H`"@`J` .
```

