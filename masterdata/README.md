The masterdata file has been in a google sheet hosted by the editor of the dataset
WHen the major editorial work has been done, the data will be converted to RDF

## Masterdata table structure 
There are two types of rows 
- Type 1: concept rows with all property values. Mandatory `A,C,D,E,L,AD`
- Type 2: rows for altLabel and hiddenLabel values and language tags. Values in column `A,F,G` or `A,H,I` only

Formatting
- Multiple values of plain literal strings are separated with character `|`.
- Language tagged literals are entered with parentheses and the tag and separated with a comma `,`.
    - E.g. `finnish text"@fi, "swedish text"@sv`
- References to Seko concepts are entered in the format `seko:nnnnn`.

## Column labels and descriptions
- list updated as of v2026-08-01
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
L skos:topConceptOf      (only one topConcept now (medium of performance) -- NEW
M skos:broader           (Full URI value, several are separated with | - mandatory value)
N skos:broader_Label     (label for the broader concept, not needed in RDF)
O editorial_issue_URL    (URL to Github issues concerning the concept)
P YSO-ID                 (skos:exactMatch object value, URL to YSO-concept)
Q wikidata-id            (skos:exactMatch, obect value, URL to Wikidata-item)
R skos:editorialNote     (rdfs:Literal)
S H&S_notation           (string rdfs:Literal, label for H-S classification link)
T H&S-ID                 (URL for skos:related object)
U MIMO-ID                (skos:exactMatch object value, URL to dbpedia)
V dbpedia                (skos:closeMatch object value, URL to dbpedia)
W SEKO-LCMPT-mapping     (property for the LCMPT relationship as a string)
X LCMPT-ID               (URL of LCMPT concept, rdfs:Literal)
Y rdfs:seeAlso           (URL of rfs:seeAlso object value, links to documentation, etc.)
Z dct:isReplacedBy       (replancing concept within the vocabulary, format seko:nnnnn)
AA skos:related           (related concept within the vocabulary, format seko:nnnnn)
AB skos:definition       (comma spearated language-tagged strings, rdf:langString)
AC skos:scopeNote        (comma spearated language-tagged strings, rdf:langString)
AD skos:changeNote       (rdfs:Literal)
AE skos:historyNote      (previous history of the concept, e.g. in earlier versions) - NEW
AF skos:modified         (last modification date,  xsd:date)
AG seko:statusNote       (string label or URI, to the selected controlled vocabulary)
AH skos:noteSeko1        (description in the finto.fi seko monolingual Finnish version) - NEW
```

Expected data structure after conversion in Turtle format
Values from the table are represented with the column label.
```
A   a skos:Concept      ;
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
    skos:statusNote    AE .    # value from controlled vocabulary?
```

skos:altLabel  and skos:hiddenLabel could be loaded as triplets directly
```
`A` skos:altLabel     "`F`"@`E` .
`A` skos:hiddenLabel  "`H`"@`J` .
```
# these need to be modelled carefully H-S notation, H-S link thinking how they are stored:
# The content editor will add only the notation (dropdown?) The link should appear automatically
#  S ;  the HS class code
#  T ;  link to the local clasas definition with local labels 
