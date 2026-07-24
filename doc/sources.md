# Source list for the ontology
Optinally show the source for the Labels, Definitions, Spatial, Temporal and other notes.

## Data model
Add [dct:source](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/#source) for any skos:Concept where it is necessary
The simplest way is to just add a URI to a rdfs:Resource i.e. an identtifer, pointing to Wikidata or to a library database record.

### If we need to describe the sources
Create a class for the sources in seko-meta:
Add the source elements in a separate .ttl file `seko-sources.ttl` which would be imported to the dataset
Add the structure of the seko-sources elements in the datamodel.

`seko-meta:Source a skos:Concept .`
Properties:
- dct:creator ;
- dct:date ;
- dct:title  ;
- dct:identifier rdfs:Literal ;  #  DOI, URI etc.
- dct:isPartOf ;  # poiter to a journal, book, or website
- dct:publisher rdfs:Resource ;
- dct:description rdfs:Literal  ; #could state what type of data bas used
- dct:relation  rdfs:Resource ;   # pointer to the resource or its description
- dct:bibliographicCitation rdfs:Literal ;  # for printed offline books?

## Add here sources that are or will be marked in the entries SEKO3

- Grove Music Online : Instrument
  - http://www.wikidata.org/entity/Q30532476
  - https://www.oxfordmusiconline.com/grovemusic/browse **(Paywall)**
- MIMO's classification - http://www.wikidata.org/entity/Q26836418
- MIMO Thesaurus of musical instrument names http://www.wikidata.org/entity/Q116920780
- Otavan iso musiikkitietosanakirja (Q116983876)
  - Otavan iso musiikkitietosanakirja osa 1, a-Dallapé
  - Otavan iso musiikkitietosanakirja osa 2 Dallapiccola - Hervé
  - Otavan iso musiikkitietosanakirja osa 3 Herz - laudes
  - Otavan iso musiikkitietosanakirja osa 4 laulu - Rantasalo
  - Otavan iso musiikkitietosanakirja osa 5 Raphaell - Öttingen

¤¤ Sources referred to in the original dataset (1998-2002)
Note! Sources were not marked in the individual records 
For referring to FINNA-records would use `@prefix finna: <https://www.finna.fi/Record/>` .
 
- Anoyanakis, Fivos. **Greek popular musical instruments.** – Athens : Melissa, 1991. – ISBN 960-204-004-1.
  - https://www.finna.fi/Record/vaari.2854463
- Baines, Anthony. **The Oxford companion to musical instruments.** – Oxford : Oxford University Press. 1992. – ISBN 0-19-311334-1.
  - https://www.finna.fi/Record/uniarts_print.991229724206249
- Brodin, Gereon. **Musiikkisanakirja.** - Helsinki : Otava, 1980. - ISBN 951-1-05506-2.
  - https://www.finna.fi/Record/fikka.3296263
- Helistö, Paavo. **Klaneetti – suomalaisen kansanklarinetin vaiheita.** – Kaustinen : Kansanmusiikki-instituutti, 1988. – (Kansanmusiikki-instituutin julkaisuja, ISSN 0355-9270 ; 27). – ISBN 951-9268-07- 3.
  - https://www.finna.fi/Record/fikka.3374639
- Hopkin, Bart. **Gravikords, Whirlies & Pyrophones : experimental musical instruments.** – Roslyn : Ellipsis Arts, 1996. – ISBN 1-5596138-2-3.
  - https://www.finna.fi/Record/vaari.1680848
- Kolehmainen, Ilkka. **Suomalaiset kansansoittimet.** – Julkaisussa: Kansanmusiikki 1980:2, s. 2 - 10.
  - https://www.finna.fi/Record/fikka.3263107
- Kuitunen, Marja-Leena & Moisala, Pirkko. **Kansojen musiikkia  : etnomusikologisia kuvauksia.** – Helsinki : Otava, 1986. – 951-1-080053-9.
  - https://www.finna.fi/Record/fikka.3298628
- Leisiö, Timo. **Islamin maiden soittimia.** – Helsinki : Suomalais-arabialainen yhdistys, 1979. – ISBN 951- 99173-8-1.
  - https://www.finna.fi/Record/fikka.3384118
- Leisiö, Timo. **Rapapallit ja lakuttimet : muinaissuomalaisia soittimia** = Fornfinländska musikinstrument = Ancient Finnish musical instruments. – Kaustinen : Kansanmusiikki-instituutti, 1985. – (Kansanmusiikki-instituutin julkaisuja, ISSN 0355-9270 ; 18). – ISBN 951-95411-5-2.
  - https://www.finna.fi/Record/arto.001485675
- Leisiö, Timo. **Suomen ja Karjalan vanhakantaiset torvi- ja pillisoittimet I : nimistö, rakenteet ja historia.** – Kaustinen : Kansanmusiikki-instituutti, 1983. – (Kansanmusiikki-instituutin julkaisuja, ISSN 0355-9270 ; 12). – ISBN 951-95410-8-X.
  - https://www.finna.fi/Record/fikka.3381118
- McGowan, Chris & Pessanha, Ricardo. **The Billboard book of Brazilian music.** – London : Guinness, 1991. – ISBN 0-85112-990-0.
  - https://www.finna.fi/Record/fikka.1221985
- Massey, Reginald & Massey, Jamila. **The music of India.** – London: Kahn & Averill, 1993. – ISBN 1-871082-50-1.
  - https://www.finna.fi/Record/vaari.1311740
- Munrow, David. **Instruments of the Middle Ages and Renaissance.** – London : Oxford University Press, 1976. – ISBN 0-19-321321-4.
  - https://www.finna.fi/Record/fikka.4618932
- **Musical instruments of the world : an illustrated encyclopedia.**  / Edited by Ruth Midgley. – S.l. : Paddington Press, 1976. – ISBN 0-8467-0134-0.
  - https://www.finna.fi/Record/fikka.167232
**The New Grove Dictionary of Musical Instruments** / Edited by Stanley Sadie. – London : Macmillan Press, 1984. – ISBN 0-333-37878-4.
  - https://www.finna.fi/Record/fikka.19134
**Otavan iso musiikkitietosanakirja 1-5.** – Helsinki : Otava, 1976-1979. – ISBN 951-1-02380-2.
  - https://www.finna.fi/Record/fikka.583420 (1, a-Dallapé)
  - https://www.finna.fi/Record/fikka.3295044 (2, Dallapiccola - Hervé)
  - https://www.finna.fi/Record/fikka.3295377 (3, Herz-laudes)
  - https://www.finna.fi/Record/fikka.3295569 (4, laulu - Rantasalo)
  - https://www.finna.fi/Record/fikka.3296061 (5, Raphael - Öttinger)
  - https://www.finna.fi/Record/fikka.3296492 (Hakemisto- ja täydennysosa)
- Pratt, Keith. **Korean music : its history and its performance.** – London : Faber & Faber, 1987. – ISBN 0-571-10081-3.
  - https://www.finna.fi/Record/fikka.22686
- Sachs, Curt. **The History of musical instruments.** – London : J. M. Dent & Sons, 1978.
  - https://www.finna.fi/Record/fikka.621334
- Saunio, Ilpo & Immonen, Kalevi. **Pororumpu ja balalaikka : Neuvostoliiton kansojen musiikki.** – Helsinki : Työväenmusiikki- instituutti, 1979. – ISBN 951-99237-5-6
  - https://www.finna.fi/Record/fikka.3384611
- Suuri musiikkitietosanakirja 1-6. – Helsinki : Weilin & Göös, 1992. – ISBN 951-35-4724-8
  - https://www.finna.fi/Record/fikka.3312782 (1, A-B)
  - https://www.finna.fi/Record/fikka.3440513 (2, C-Ha)
  - https://www.finna.fi/Record/fikka.3447402 (2, He-Kuud)
  - https://www.finna.fi/Record/fikka.3472596 (4, Kuul-N)
  - https://www.finna.fi/Record/fikka.3505625 (5, O-See)
  - https://www.finna.fi/Record/fikka.3531122 (6, Seg-Ö)
- Waring, Dennis. **Folk instruments : make them and play them.** – London : Hyperion Press, 1979. – 0-920534- 06-6.
  - https://www.finna.fi/Record/vaari.1187885
  
