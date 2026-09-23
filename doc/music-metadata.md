# Mitä on musiikin metadata? - What is music metadata? 

### Lähteitä - Sources
- Tuomas Talonpoika, Gramex:  [Musiikin metadata: Osa 1. Mitä ja miksi?](https://www.gramex.fi/musiikin-metadata-mita-ja-miksi/) - intended audience: musicians.
- Turo Pekari, Teosto (2020):  [Metadata on musiikkialan suuri ongelma ja suuri mahdollisuus](https://www.teosto.fi/teostory/metadata-on-musiikkialan-suuri-ongelma-ja-suuri-mahdollisuus/)
- J. Muikku, Suomen musiikintekijät (2017) [Musiikkitiedostojen metadata](https://musiikintekijat.fi/sites/default/files/metadata_170925_final.pdf) (PDF)

### Kirjastot - Libraries
- [Musiikin RDA-sovellusohje](https://wiki.helsinki.fi/xwiki/bin/view/rdasovellusohje/RDA-kuvailu%20MARC%2021%20-formaatilla/Musiikin%20RDA-sovellusohje/)  - [382 Esityskokoonpano](https://wiki.helsinki.fi/xwiki/bin/view/rdasovellusohje/RDA-kuvailu%20MARC%2021%20-formaatilla/Musiikin%20RDA-sovellusohje/06.%20Fyysisen%20kuvailun%20jne.%20kent%C3%A4t%20%283XX%29/#H382ESITYSKOKOONPANO28T29)
- Muska Working Group, Finnish Music Library Association: [Music information search](https://www.musiikintiedonhaku.fi/en/)


## Soittimet kirjastoformaateissa - Music instruments in library data formats
### MARC21
- [048 - SOITINTEN JA LAULUÄÄNTEN KOODI JA MÄÄRÄ (T)](https://marc21.kansalliskirjasto.fi/bib/01X-04X.htm#048) - sis. Soitinten ja äänialojen MARC 21 -koodit. [en: marcmusperf](https://www.loc.gov/standards/valuelist/marcmusperf.html)
    - 048 - Number of Musical Instruments or Voices Codes (R)  [Full](https://www.loc.gov/marc/bibliographic/bd048.html) | [Concise](https://www.loc.gov/marc/bibliographic/concise/bd048.html)
- [382 - ESITYSKOKOONPANO (T)](https://marc21.kansalliskirjasto.fi/bib/3XX.htm#382)
    - 382 - Medium of Performance (R)  [Full](https://www.loc.gov/marc/bibliographic/bd382.html) | [Concise](https://www.loc.gov/marc/bibliographic/concise/bd382.html)
- [511 - HUOMAUTUS OSALLISTUJISTA TAI ESITTÄJISTÄ (T)](https://marc21.kansalliskirjasto.fi/bib/50X-53X.htm#511)
    - 511 - Participant or Performer Note (R)  [Full](https://www.loc.gov/marc/bibliographic/bd511.html) | [Concise](https://www.loc.gov/marc/bibliographic/concise/bd511.html)

### Bibframe [v 3.0.1](http://id.loc.gov/ontologies/bibframe-3-0-1/)
Situation as of Autumn 2026, but there may be changes in the future through inclusion of elements from [Performed Music Ontology](https://performedmusicontology.org/ontology/PMO.html)?
- see MLA: [Bibframe 3.0 now with improved music data](https://cmc.wp.musiclibraryassoc.org/2026/02/03/bibframe-3-0-now-with-improved-music-data/)

#### Classes:
- [bf:MusicEnsemble](https://id.loc.gov/ontologies/bibframe.html#c_MusicEnsemble) - Ensemble for which a musical work is appropriate
    - subClass of [bf:Ensemble](https://id.loc.gov/ontologies/bibframe.html#c_Ensemble) - Composition of the ensemble, including the size of the ensemble and the medium of performance components
- [bf:MusicInstrument](https://id.loc.gov/ontologies/bibframe.html#c_MusicInstrument) - Instrument for which a musical work is appropriate
- [bf:MusicMedium](https://id.loc.gov/ontologies/bibframe.html#c_MusicMedium) - Summary statement of the medium for a musical work
- [bf:MediumComponent](https://id.loc.gov/ontologies/bibframe.html#c_MediumComponent) - An individual component of a medium of performance, gathering together the medium of performance, medium count, number of hands, and component qualifier
- [bf:MediumComponentQualifier](https://id.loc.gov/ontologies/bibframe.html#p_mediumComponentQualifier) - Relates a medium component to a qualifier that affects the medium of component
- [bf:MediumOfPerformance](https://id.loc.gov/ontologies/bibframe.html#c_MediumOfPerformance) - An individual instrument, voice, ensemble, or instrumental group

#### Properties
- [bf:ensemble](https://id.loc.gov/ontologies/bibframe.html#p_ensemble) - Composition of the ensemble applicable to the Work
- [bf:instrument](https://id.loc.gov/ontologies/bibframe.html#p_instrument) - Instrument for which a musical Work is appropriate  
- [bf:instrumentalType](https://id.loc.gov/ontologies/bibframe.html#p_instrumentalType) - Specific role of instrument, such as alternate, doubling, solo, ensemble  
- [bf:mediumComponent](https://id.loc.gov/ontologies/bibframe.html#p_mediumComponent) -	Relates a work to a medium component  
- [bf:mediumComponentQualifier](https://id.loc.gov/ontologies/bibframe.html#p_mediumComponentQualifier) - Relates a medium component to a qualifier that affects the medium of component  
- [bf:mediumOfPerformance](https://id.loc.gov/ontologies/bibframe.html#p_mediumOfPerformance) - Relates a work to a musical medium of performance  
- [bf:musicMedium](https://id.loc.gov/ontologies/bibframe.html#p_musicMedium) - Instrumental, vocal, and/or other medium of performance for which a musical resource was originally conceived, written or performed.
- [bf:usesMediumOfPerformance](https://id.loc.gov/ontologies/bibframe.html#p_usesMediumOfPerformance) - The medium of performance used by a contributing agent  
