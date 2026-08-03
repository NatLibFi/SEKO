Some terminology for Swedish interface of SEKO3

Tämä sanasto on luonnos SKOS-standardin (Simple Knowledge Organization System) mukaiseen tietomallinnukseen, Turtle-formaattiin sekä sanastojen käyttöliittymiin ja kuvailutyöhön.

Huom! Tarkista termien yhteensopivuus [Libriksen](https://id.kb.sv/vokab) sanaston kanssa.
Näistä pyritään kuitenkin käyttämään ensisijaisesti Skosmos käyttöliittymän oletusarvoja, kun sellainen on käytettävissä.

| English | Suomi | Svenska | SKOS / Tekninen vastine |
| :--- | :--- | :--- | :--- |
| Classes | Luokat | **Klasser** | `rdfs:Class` / `owl:Class` |
| Properties | Ominaisuudet | **Egenskaper** | `rdf:Property` |
| Object property | Olio-ominaisuus | **Objektegenskap** | `owl:ObjectProperty` |
| Datatype property | Arvottyyppiominaisuus | **Datatypsegenskap** | `owl:DatatypeProperty` |
| Label | Nimi / Termi | **Term** (tai *Etikett*) | `rdfs:label` / `skos:xl:Label` |
| Note | Huomautus | **Anmärkning** | `skos:note` |
| Concept | Käsite | **Begrepp** | `skos:Concept` |
| broader | laajempi | **Bredare** | `skos:broader` |
| narrower | suppeampi | **Smalare** | `skos:narrower` |
| Scheme | skeema / käsite-edustusto | **Konceptschema** | `skos:ConceptScheme` |
| ontology | ontologia | **Ontologi** | `owl:Ontology` |
| vocabulary | sanasto | **Vokabulär** (tai *Ordlista*) | Yleistermi |
| deprecated | vanhentunut (poistettu) | **Föråldrad** | `owl:deprecated` |
| broader class | yläluokka | **Superklass** | `rdfs:subClassOf` |
| narrower class | alaluokka | **Subklass** | Luokkahierarkia |
| Local | Paikallinen | **Lokal** | Alueellinen / Nimiavaruus |
| External | Ulkoinen | **Extern** | Ulkopuolinen linkitys |
| Preferred label | Suositettava termi | **Föredragen term** | `skos:prefLabel` |
| Alternative label | Vaihtoehtoinen termi | **Alternativ term** | `skos:altLabel` |
| Hidden label | Piilotettu termi | **Dold term** | `skos:hiddenLabel` |
| Related (concept) | Lähikäsite / Assosiatiivinen | **Relaterat begrepp** | `skos:related` |
| Top concept | Top-käsite / Ylinkäsite | **Toppbegrepp** | `skos:hasTopConcept` |
| Collection | Kokoelma | **Kollektion** | `skos:Collection` |
| Member | Jäsen | **Medlem** | `skos:member` |
| Scope note | Käyttöalaan liittyvä huomautus| **Omfångsnote** (tai *Användningsomfång*)| `skos:scopeNote` |
| Definition | Määritelmä | **Definition** | `skos:definition` |
| Editorial note | Toimituksellinen huomautus | **Redaktionell anmärkning**| `skos:editorialNote` |
| History note | Historiatieto | **Historiknot** | `skos:historyNote` |
| Notation | Notaatio / Koodi | **Notation** | `skos:notation` |
| Exact match | Tarkan vastaavuuden linkki | **Exakt matchning** | `skos:exactMatch` |
