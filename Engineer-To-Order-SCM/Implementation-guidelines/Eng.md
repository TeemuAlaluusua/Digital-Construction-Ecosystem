# Implementation guideline for unique product identification and data carrier interoperability

**Engineer-To-Order Construction products**  
>Julkaisija: Rakennusteollisuus ry\
>Release: 23.6.2025  
Versio: 1.3  
Status: Released



## Document information
<details> 
<Summary>Log of changes</Summary>
 
| **Release**| **Date of change**| **Changed by**  |**Summary of change**                              |
|------------|-------------------|-----------------|---------------------------------------------------|
| 1.0        | 2024-12-10        |TAla             | Asiakirja julkaistu                               |
| 1.1        | 2024-12-16        |TAla             | Added missing information and corrected typos     |
| 1.2        | 2025-01-09        |TAla             | Added missing information and corrected typos     |
| 1.3        | 2025-06-17        |TAla             | Added missing information and corrected typos     |
</details>

<details> 
<Summary>Contributors</Summary>

| **Name**            | **Organisation**               |
|---------------------|--------------------------------|
| Teemu Alaluusua     | Aalto-yliopisto                |
| Juuso Autiosalo     | Aalto-yliopisto                |
| Petri Leppänen      | GS1 Finland Oy                 | 
| Tom Partanen        | Consolis Parma Oy              |
| Eetu Lahtinen       | Consolis Parma Oy              |
| Janne Kihula        | Rakennustuoteteollisuus RTT ry |
| Veijo Artoma        | Consolis Parma Oy              |
| Kari Turunen        | Lujabetoni Oy                  |
| Ville Retulainen    | Lujabetoni Oy                  |
| Markku Räisänen     | Betset Oy                      |
| Otto Alhava         | Fira Oy                        |
| Tuomas Kekki        | Fira Oy                        |
| Hannes Ilveskoski   | Fira Oy                        |
| Antti Pekkala       | Fira Oy                        |
| Ari Törrönen        | NCC Suomi Oy                   |
| Riku Laiho          | NCC Suomi Oy                   |
| Arto Nieminen       | NCC Suomi Oy                   |
| Janne Makkonen      | Consti                         |
| Ville Siikaoja      | YIT                            |
| Lassi Saari         | YIT                            |
| Klaus Turhanen      | RFID Lab Finland ry            |
| Janne Raitaniemi    | Riffid Oy                      |
| Juha Porkka         | Nordic ID Oyj                  |
| Sami Saari          | Rakennustieto Oy               |
| Teemu Rantanen      | Rakennustieto Oy               |
</details>

## 1 Background
Unique Product Identification (UPID) and Automatic Identification and Data Capture (AIDC) carriers for construction products are key components of digitalization in the real estate and construction sector. Standardized, interoperable, and globally adopted methods for product identification and data capture ensure consistent and reliable information exchange among stakeholders, regardless of their role in the supply chain.

The supply chain management standards developed by GS1, such as the GTIN product identifier combined with the EAN barcode, enable consistent information exchange between different stakeholders. The GTIN product identifier allows the identification of any trade item that can be priced, ordered, or invoiced at any stage of the supply chain, where predefined information needs to be retrieved.

In the retail sector, products have been identified using GTIN codes and machine-readable 1D EAN barcodes for over 50 years. This proven practice has now become established for Make-To-Stock (MTS) construction products as well. However, in the Finnish construction industry, Engineer-To-Order (ETO) products are widely utilized, and the methods for their identification and recognition have not yet been standardized.

The identification of construction products is critical from the perspective of information exchange, as the lifespan of these products is typically long, with some remaining in active use for over 100 years. The rapid development of new materials, along with the growing importance of sustainability and the circular economy, has increased the need to manage construction products and their properties throughout their lifecycle.

## 2 Purpose of this guideline
This implementation guideline has been created as part of the Confederation of Finnish Construction Industries RT's (Rakennusteollisuus RT) development project on product information and supply chain digitalization, led by the BETK working group. The primary goal of the development project is to advance the methods for managing the construction industry's product supply chain, transitioning from manual and unstructured information exchange to fully structured and machine-readable data exchange. This document is continuously updated and further developed based on findings from the ongoing development efforts of Rakennusteollisuus RT.

The implementation guideline focuses on the product identification and data capture required for the digitalization of the supply chain. It outlines a model for applying open GS1 standards to manage the supply chain of Engineer-to-Order (ETO) construction products, using precast concrete elements as an example.

GS1 is conducting international standardization work related to the identification of Engineer-to-Order and Made-to-Order products. As this guideline was created while the standardization process is ongoing, it may be updated as necessary to align with finalized standards.

## 3 SGTIN product identification of construction products
Unique Product Identification (UPID) is a prerequisite for the digitalization of the supply chain, regardless of the manufacturing logic of the products. For precast concrete elements, product identification has been designed to scale by leveraging an open, product-group-independent, and international standard. The GTIN code, compliant with GS1 standards, is a widely used solution for product identification across various industries. Its application was selected as the foundation for identifying Engineer-To-Order (ETO) products, such as precast concrete elements, within this project.

Traditionally, GTIN codes have been used to identify Make-To-Stock (MTS) products, where all identical items are assigned the same GTIN. By combining a GTIN code with a serial number, a unique identifier is created that allows identical products to be distinguished from one another. This combination is known as the SGTIN (Serialized Global Trade Item Number).

Precast concrete elements are inherently Make-To-Order (MTO) and Engineer-To-Order (ETO) products, meaning their identification using GTIN codes differs fundamentally from that of Make-To-Stock (MTS) products. While it is possible to assign a unique GTIN code to each individual precast element, the BETK working group has opted to use the GS1 standard with a three-level identification model (as shown in Table 1). In this model the GTIN code identifies a specific base product type from a specific manufacturer. The Made-To-Order (MTO) variant number distinguishes a particular variant of the base product. The serial number uniquely identifies identical units of the same variant.

Thus, a GTIN alone does not uniquely identify a specific product but rather represents a general category of possible product variations that may be manufactured based on the order.

![2025-06-23_Kuva3](https://github.com/user-attachments/assets/9fa68e30-01da-458f-8cb4-9c80be84a9bb)

###### Figure 1.  Hierarchical Levels of Product Identification for More Precise Identification

### 3.1 Using GS1 application identifiers to identify ETO products  
GS1 Application Identifiers (AI) are numeric prefixes used in barcodes and EPC/RFID tags to define the meaning and format of data elements. The use of AIs enables the differentiation of various data elements within barcodes or EPC/RFID tags. The GS1 standard includes over 100 application identifiers. Each AI is typically a two-, three-, or four-digit number. A comprehensive list of all GS1 Application Identifiers is available on the GS1 website:https://ref.gs1.org/ai/.

he following GS1 Application Identifiers (AIs) have been identified as necessary to meet the minimum data requirements for the identification of precast concrete elements:
• ```(01) GTIN```: Global Trade Item Number – identifies the base product type.
• ```(242) Made-to-Order Variation Number```: Distinguishes a specific variant of the base product.
• ```(21) Serial Number```: Uniquely identifies individual units of the same variant.

The GS1 standard does not currently provide specific GS1 Application Identifiers (AIs) for the National Element Classification number, GUID, or Domain Name. Therefore, the BETK project has decided to use the following application identifiers for including this data in information carriers:
• ```(91) Company Internal Information```
• ```(92) Company Internal Information```
• ```(99) Company Internal Information```

GS1 AIs starting with the digit 9 are reserved for company-specific or internal use and should only be applied when there is no official GS1 Application Identifier defined for the particular data element. This approach ensures flexibility while adhering to GS1 standards for data structuring.

Note! At the time of this guideline's publication, the handling of domain names in RFID tags is under review within GS1's international standard development process. The forthcoming standard may differ from the solution presented here, and this guidance will be updated accordingly once the standard is finalized.

For optical recognition (e.g., QR codes), the inclusion of this information follows the procedure outlined in the GS1 Digital Link URI Syntax 1.5.0 standard.

###### Table 1. Minimum data requirements to be included in the information carrier (2D DataMatrix Barcode or EPC/RFID Tag)

| GS1 Application Identifier (AI) | Example                      |
|------------------------- -------|------------------------------|
|(01) GTIN-koodi                  | <code>06400001000247</code>  |
|(242) MTO varianttinumero        | <code>123456</code>          |
|(21) Sarjanumero                 | <code>12345678910</code>     | 

###### Taulukko 2.Tiedonkantajaan lisättävät valinnaiset lisätiedot. *Huom! Optisessa tunnistamisessa (esim. QR-koodi) verkkotunnuksen sisällyttämisessä käytetään GS1 Digital Link URI syntax 1.5.0 -standardin mukaista menettelyä

| Sovellustunnus (AI) | Tieto           | Esimerkki                                         |
|---------------------|-----------------|---------------------------------------------------|
| (91)                | Elementtitunnus | <code>V1001</code>                                |
| (92)                | GUID            | <code>ba34cf17-0c4b-4c6f-9295-cae05aa74ad4</code> |
| (99)                | Verkkotunnus    | <code>id.rt.fi </code>                            |

### 3.2 GS1- yritystunniste
GS1-yritystunnus, eli GS1 Company Prefix, on yksilöllinen numerosarja, jonka GS1-organisaatio myöntää yrityksille maailmanlaajuisesti. Yritystunniste on asiakaskohtainen, eikä samaa tunnistetta tai sen pohjalta tehtyjä numerosarjoja voi olla minkään muun toimijan käytössä. GS1-yritystunnusta käytetään monissa standardoiduissa tunnistusmenetelmissä, kuten viivakoodeissa ja RFID-tunnisteissa, ja se on pohjana GTIN-, GLN- ja SSCC-koodien muodostamisessa.

Suomessa GS1-yritystunnisteita myöntää GS1 Finland ja sellaisen voi tilata GS1 Finlandin verkkokaupasta. Oikean GS1-yritystunnisteen valinnassa tulee huomioida tarvittavien GTIN-koodien määrä, johon on tarvittaessa saatavilla apua GS1 Finlandin asiakaspalvelusta.

### 3.3 GTIN-koodin muodostaminen
GTIN-koodien muodostaminen edellyttää, että yrityksellä on käytettävissään GS1-yritystunniste (GS1 Company Prefix, GCP). GTIN-koodien muodostaminen taas mahdollistaa tuotteiden yksilöllisen tunnistamisen perustuotteen tasolla.

GTIN-koodi alkaa GS1-yritystunnisteella, jonka pituus GS1 Finlandilta saatavilla olevilla vaihtoehdoilla voi olla 7–11 numeroa. Tämän jälkeen seuraavat 1–6 numeroa voi määrittää itse, ja näissä suositellaan käytettäväksi juoksevaa numerointia. Käytettävissä olevien numeroiden määrä riippuu yritystunnisteen pituudesta. Koodin viimeinen, eli 13. numero, on tarkistusnumero, joka lasketaan 12 ensimmäisen numeron perusteella Modulo 10 -algoritmilla. Tarkistusnumeron laskemiseen voi käyttää esimerkiksi GS1 Finlandin tarjoamaa tarkistusnumerolaskuria: https://gs1.fi/fi/tarkistusnumerolaskuri

###### Taulukko 3. GTIN-koodin rakenne

| GS1-sovellustunnus | GS1-yritystunniste ---> <--- tuotekohtainen numero     |  Tarkistusnumero |
|--------------------|--------------------------------------------------------|------------------|
| (01)               |  <ins>0</ins> N1 N2 N3 N4 N5 N6 N7 N8 N9 N10 N11 N12   | N13              |
 
Viivakoodeissa ja RFID-tunnisteissa GTIN-koodin ilmaisemiseen käytettävä sovellustunnus on (01). GS1:n kansainvälisessä standardikehityksessä käsitellään parhaillaan tilauksesta valmistettavien ja tilauksesta suunniteltavien tuotteiden yksilöintiä. Tämän standardinkehitystyön tuloksena voi tulla muutoksia tilauksesta valmistettavien/suunniteltavien tuotteiden GTIN-koodien ilmaisemiseen. Tämä ohje päivitetään standardin valmistuessa.

Huom! GTIN-koodin pisin versio on 14-merkkiä pitkä ja tätä lyhyemmät GTIN-koodit täydennetään koodin eteen lisättävillä nollilla 14-merkkiä pitkiksi. GTIN-koodi ei voi olla tätä pidempi.

GS1 Finland tarjoaa yritystunnisteasiakkailleen käyttöön GS1 Rekisteri -palvelun GTIN-koodien muodostamiseen. Muodostamalla GTIN-koodin GS1 Rekisteri -palvelussa, voi varmistua niiden oikeasta muodosta.

### 3.4 Variaatioiden yksilöinti
Betonielementtien variaatioiden yksilöinnissä GTIN-koodiin yhdistetään lisätunnisteena variaationumero (Madeto-Order variation number). Variaationumero mahdollistaa sen, että voidaan tietää joidenkin elementtien olevan keskenään samanlaisia. Toisin sanoen, kun monta elementtiä, joilla on samat tekniset tiedot, valmistetaan kerralla, niillä kaikilla on sama GTIN-koodin ja variaationumeron yhdistelmä.

Viivakoodeissa ja RFID-tunnisteissa käytetään sovellustunnusta <code>(242)</code> ilmaisemaan variaationumero. GS1-standardin mukaan variaationumero on numeerinen ja vaihtuvapituinen, enintään kuusi numeroa pitkä.

###### Taulukko 4. MTO-Varianttinumero-koodin rakenne

| GS1-sovellustunnus | Made-to-Order variation number |
|--------------------|--------------------------------|
| (242)              | N1 ----vaihtuva pituus --->N6  |

### 3.5 Sarjanumerointi
Yhdistämällä GTIN-koodiin (tai GTIN-koodin ja variaationumeron yhdistelmään) sarjanumerointi, voidaan yksilöidä ja erottaa toisistaan keskenään identtiset elementit. GS1-sovellustunnus (21) osoittaa, että tietokenttä sisältää sarjanumeron. GS1-standardin mukaan sarjanumero on aakkosnumeerinen ja enintään 20 merkkiä pitkä.
Huom! Valittu RFID-tunniste voi asettaa rajoituksia sarjanumeron pituudelle ja aakkosten käytölle, joten asia on hyvä tarkistaa RFID-ratkaisutoimittajalta.
###### Taulukko 5. Sarjanumero-koodin rakenne

| GS1-sovellustunnus | Serial number                  |
|--------------------|--------------------------------|
| (21)               | X1 ----vaihtuva pituus --->X20 |

### 3.6 Elementtitunnus
Elementille määritetty tunnus, joka on ihmisen helposti luettavissa, ja voi sisältää tietoa esimerkiksi elementin
tyypistä tai asennuskerroksesta. Elementtitunnuksen ei tarvitse olla globaalisti yksilöllinen.

###### Taulukko 6. Elementtitunnukset rakenne

| GS1-sovellustunnus | Elementtitunnus                |
|--------------------|--------------------------------|
| (91)               | X1 ----vaihtuva pituus --->X20 |

### 3.7 GUID
GUID, toiselta nimeltään UUID, on globaalisti yksilöllinen tunnuste, joka voidaan määrittää mallinnusohjelman toimesta tai muulla yksilöllisyyden varmistavalla tavalla.

###### Taulukko 7. GUID-koodin rakenne

| GS1-sovellustunnus | GUID                                 |
|--------------------|--------------------------------------|
| (92)               | xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx |

### 3.8 Verkkotunnus
Yhdistämällä verkkotunnus ja muita yksilöintitietoja voidaan hakea internetin välityksellä lisätietoja yksilöidystä
tuotteesta URL-osoitteen avulla, mikäli tietojen toimittaja on toteuttanut ominaisuuden ja pitää sitä edelleen
toiminnassa.

###### Taulukko 8. Verkkotunnuksen rakenne. * Huom! Optisessa tunnistamisessa (esim. QR-koodi) tämän tiedon sisällyttämisessä käytetään edellä esitetyn GS1 Digital Link URI syntax 1.5.0 -standardin mukaista menettelyä.

|GS1-sovellustunnus |Verkkotunnus                                                          |
|-------------------|----------------------------------------------------------------------|
|(99)               |<alitunnus.><tunnus.ylätunnus>, jossa <alitunnus.> toistuu 0…n kertaa)|

Tässä dokumentissa määritellään kaksi tapaa yhdistää verkkotunnus muihin yksilöintitietoihin URL-osoitteen muodostamiseksi. Tuloksena muodostuu GS1 Digital Link -standardin tai IEC 61406 -standardin mukainen URLosoite.  

#### 3.8.1 GS1 Digital Link URL-osoitteen muodostaminen
GS1 Digital Link on GS1:n määrittämä standardi miten verkkotunnuksen avulla voidaan määrittää tuotteelle URLosoite. GS1 ei kuitenkaan ole määritellyt miten verkkotunnuksen voisi kirjoittaa RFID-tunnisteeseen kun halutaan määrittää GS1 Digital Link yksilötasolla. (Määritys on GS1:ssä työn alla, mutta toistaiseksi BETK:ssa noudatetaan omaa tapaa.)

BETK soveltamisohjeen mukaisesti GS1 Digital Link muodostetaan seuraavasti:  
**Yksilöinnin Taso 1:** ```https://<verkkotunnus>/01/<GTIN>```  
**Yksilöinnin Taso 2:** ```https://<verkkotunnus>/01/<GTIN>/242/<MTO varianttinumero>```  
**Yksilöinnin Taso 3:** ```https://<verkkotunnus>/01/<GTIN>/242/<MTO varianttinumero>/21/<sarjanumero>```  
**Taso 3 kun ei varianttinumeroa määritetty:** ```https://<verkkotunnus>/01/<GTIN>/21/<sarjanumero>```  
Viimeiselle tapaukselle esimerkiksi muodostuu: https://id.rt.fi/01/06400001000247/21/12345678910  
GS1 Digital Link -standardista on kerrottu lisää tämän ohjeen kappaleessa 4.3.  

#### 3.8.2 IEC 61406 Identification Link muotoisen URL-osoitteen muodostaminen
Lisäksi voidaan määrittää GUID-tunnisteeseen perustuva IEC 61406 Identification Link standardin mukainen URL-osoite seuraavasti:  

```https://<verkkotunnus>/<GUID>```  

Jolloin esimerkiksi muodostuu: <code>https://id.rt.fi/ba34cf17-0c4b-4c6f-9295-cae05aa74ad4</code>

## 4 Automaattinen tunnistaminen ja tiedonkantajat
Tuoteyksilöinnin lisäksi on valittava käytettävä tunnistusteknologia ja tiedonkantaja, jotka mahdollistavat niiden koneellisen luennan. Tunnistusteknologian valinnassa tulee huomioida käyttötarkoituksen ja olosuhteiden asettamat vaatimukset. Automaattiseen tunnistamiseen ja tiedonkeruuseen tarkoitettuihin GS1-tietokantajiin voidaan tallentaa erilaisia tietomääriä eri liiketoimintaprosesseja ja kaupankäynnin vaatimuksia varten. GS1-tietokantajiin koodatut tiedot eivät ainoastaan yksilöi tuotteita yksiselitteisesti kaikilla Tuoteyksilöinnin hierarkia tasoilla, vaan ne tarjoavat myös pääsyn tuotetietoihin ja näkyvyyden tuotteiden liikkeisiin toimitusketjussa.  

Betonielementtien tuotetunnistamisen minimitietovaatimusten välittämisessä soveltamisohje suosittelee vähintään optiseen tunnistamiseen perustuvan 2D-koodin lisäämistä elementin tuote-etikettiin valmistuksen yhteydessä. GS1-standardissa vaihtoehdot tähän ovat GS1 DataMatrix -koodi sekä QR-koodi GS1 Digital Link -standardin mukaisella tietosisällöllä. Elementin tuote-etiketissä käytettävän 2D-koodin rinnalla, voidaan käyttää myös RFID-teknologiaan perustuvaa koneluettavaa tiedonkantajaa, joko elementin tuote-etiketissä tai betonielementtiin valettuna. Kuvassa 1 on esitetty tiedonkantajien käyttöä ja merkintää betonielementtien osalta.

Tässä soveltamisohjeessa on kuvattu tuotetunnistusta GS1 DataMatrix -koodin avulla, joka soveltuu BETK-työryhmässä määritettyyn käyttötarkoitukseen. Vaihtoehtona on esitelty lyhyesti myös GS1 Digital Link -standardin mukainen QR-koodi ja sen hyödyntämisen mahdollisuuksista on tarvittaessa saatavissa lisätietoa GS1 Finlandilta.  

![2025-06-23_Kuva1](https://github.com/user-attachments/assets/f1e26ff8-63e8-48e5-8808-ce45a36583b8)

###### Kuva 2. Koneellinen tuotetunnistaminen GS1-tiedonkatajien avulla

Betonielementtien automaattisessa tunnistamisessa tehokkaimmaksi tiedonkantajaksi on havaittu EPC/RFID
Gen-2 UHF -standardiin perustuva passiivinen etäluettava tunniste, josta elementin tunnistenumero voidaan lukea tehokkaasti myös useampien metrien päästä ilman suoraa näköyhteyttä itse tunnisteeseen.

### 4.1 Tuotetunnistus passiivisella EPC/RFID Gen2 UHF -tunnisteella
Tämä ohje perustuu EPC / RFID Gen2 Radio -protokollaan, joka määrittelee fyysisen tiedonsiirron RFID-sirun ja RFID-lukijan välillä käskyillä RFID-lukijan ohjaamiseksi suhteessa RFID-tunnisteisiin. EPC / RFID Gen2 on ISO-standardi ja kattaa erilaisia toiminnallisuuksia, kuten suojauksen ja laajennetun käyttäjämuistin.

GS1 on julkaissut TDS:n (Tag Data Standard), joka määrittelee miten GS1-standardin mukaiset yksilöintiavaimet, kuten SGTIN sisällytetään etäluettaviin EPC Gen2 RFID -tunnisteisiin. TDS-standardi on avoimesti kaikkien käytettävissä ja se onkin jo nykyisin laajasti käytössä RFID-tunnistamisessa eri toimialoilla.

Tuotetunnistuksessa vaadittavat tiedot sisällytetään EPC Gen2 RFID -tunnisteisiin TDS-standardin mukaisesti, tarvittavia GS1-sovellustunnuksia hyödyntäen. Tietojen koodaamiseen käytetään tunnisteen EPC-muistia (EPC memory) ja tarvittavilta osin käyttäjämuistia (User memory).

EPC-muisti on suunniteltu sisältämään EPC-koodi, eli tunnistettavan asian yksilöivä GS1-standardin mukainen tunnistenumero. Betonielementtien yksilöinnissä EPC-muistiin koodataan elementin SGTIN-koodi. Tämä mahdollistaa elementin yksilöivän tunnistenumeron nopean lukemisen.

Käyttäjämuistia käytetään, kun RFID-tunnisteelle on tarve saada enemmän tietoa kuin EPC-muistiin mahtuu.  
BETK-projektissa on tunnistettu, että tunnisteeseen on tarve sijoittaa lisätietoa kuten variaationumero (Madeto-Order Variation Number), elementtien luokittelussa käytettävä elementtitunnus ja suunnitteluohjelmiston luoma GUID-tunniste. GTIN:n ja SGTIN:n rakenne viivakoodeissa ja EPC/RFID Gen 2V2 RFID-tunnisteissa

###### Taulukko 9. Käytössä olevat EPC-binäärikoodausjärjestelmät ja niiden rajoitukset. Sovellettava menetelmä määräytyy numeeristen tai alfanumeeristen merkkien määrätarpeen mukaan.

<html>
<table>
    <thead>
        <tr>             
           <th>EPC järjestelmä</th>
           <th>EPC-binaarikoodausjär-jestelmä</th>
           <th>EPC + suodatin-bittimäärä</th>
           <th>Sisältää suodatinarvon</th>
           <th>Sarjanumerorajoitus</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="2">sgtin</td>
            <td>sgtin-96</td>
            <td>96</td>
            <td>Kyllä</td>
            <td>Vain numerot; ei alkavia nollia, desi-maaliluvun arvo alle 2³⁸ (eli desimaali-luku enintään 274 877 906 943).</td>
        </tr>
        <tr>
            <td>sgtin-198</td>
            <td>198</td>
            <td>Kyllä</td>
            <td>Kaikki GS1 General Specifications -määritysten sallimat arvot (enintään 20 aakkosnumeerista merkkiä).</td>
        </tr>
    </tbody>
</table>
</html>

###### Taulukko 10. Sovellettava menetelmä SGTIN-96. Standardissa TDS 2.1. (EPC Tag Data Standard) löytyy myös muita sovellusmenetelmiä mm. SGTIN-198, joita voidaan käyttää, mikäli on tarve esimerkiksi pidemmälle (tai numeroiden lisäksi myös kirjaimia sisältävälle) sarjanumerolle.

<html>
<table>
    <thead>
        <tr>             
         <th colspan="3">SGTIN-96 tietosisältö</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>EPC SGTIN-96</b></td>
            <td><b>Arvo</b></td>
            <td><b>Kommentti</b></td>
        </tr>
        <tr>
            <td>Otsikko (Header)</td>
            <td><code>48</code></td>
            <td>Numero SGTIN-96:lle</td>
        </tr>
      <tr>
            <td>Filter-arvo (Filter value)</td>
            <td><code>0</code></td>
            <td>0 = Soveltuva arvo tuotteelle, jota ei lueta kassapisteellä</td>
        </tr>
         <tr>
            <td rowspan="6">Partition-arvo</td>
            <td rowspan="6"><code>1</code>,<code>2</code>,<code>3</code>,<code>4</code>,<code>5</code>tai <code>6</code></td>
            <td>
              1 = 11-numeroinen GS1-yritystunniste ja 2 numeroa tuotenimikkeelle + laajennustunnukselle                                        
            </td>
        </tr>
        <tr>
            <td>2 = 10-numeroinen GS1-yritystunniste ja 3 numeroa tuotenimikkeelle + laajennustunnukselle </td>
        </tr>
       <tr>
            <td>3 = 9-numeroinen GS1-yritystunniste ja 4 numeroa tuotenimikkeelle + laajennustunnukselle</td>
        </tr>
       <tr>
            <td>4 = 8-numeroinen GS1-yritystunniste ja 5 numeroa tuotenimikkeelle + laajennustunnukselle</td>
        </tr>
        <tr>
            <td>5 = 7-numeroinen GS1-yritystunniste ja 6 numeroa tuotenimikkeelle + laajennustunnukselle</td>
        </tr>
        <tr>
            <td> 6 = 6-numeroinen GS1-yritystunniste ja 7 numeroa tuotenimikkeelle + laajennustunnukselle </td>
        </tr>
         <tr>
          <td>GS1-yritystunniste (GS1 GCP)</td>
          <td><code>N…11</code></td>
          <td>GS1-yritystunniste: 6,7,8,9,10 tai 11 numeroa</td>
         </tr>
        <tr>
          <td>Tuotenimikkeen numero</td>
          <td><code>N…7</code></td>
          <td>Riippuen GS1-yritystunnisteen pituudesta 1–7 numeroa</td>
        </tr>
         <tr>
          <td>Sarjanumero </td>
          <td><code>N…12</code></td>
          <td>Enintään 12 numeroa (suurin sallittu arvo = 274 877 906 943) Sarjanumeron ei tarvitse olla tasan 12 numeroa. Etunolla ei ole sallittu</td>
        </tr>
    </tbody>
</table>
</html>

**Esimerkki tietosisällöstä EPC / Gen2 RFID -tunnisteessa:**  
RFID Tag EPC Memory Bank Contents (hexadecimal): ```301586A004000602DFDC1C3E```  
EPC Tag URI: ```urn:epc:tag:sgtin-96:0.6400001.000024.12345678910```  

**Tietorakenteen osat**  
**1. URN-etuliite**  
Arvo: ```urn:epc:id```  
Kuvaus: Määrittää, että tunniste noudattaa EPC URI -standardia. Tämä etuliite on osa Uniform Resource Identifier (URI) -kehystä.  
**2. EPC-järjestelmä**  
Arvo: ```sgtin-96```  
Kuvaus: Määrittää koodaustavan ja käytetyn GS1-tunnistusavaimen tyypin. Tässä tapauksessa kyseessä on Serialized Global Trade Item Number (SGTIN), joka on 96-bittisesti binäärikoodattu.  
**3. Suodatusarvo**  
Arvo: ```0```  
Kuvaus: Ilmoittaa suodatusasetuksen. Arvo 0 tarkoittaa, että tuotetta ei ole suodatettu myyntipisteellä tapahtuvan skannauksen perusteella, mikä viittaa yleiskäyttöön.  
**4. GS1-yritystunniste**  
Arvo: ```6400001```  
Kuvaus: Tunnistaa yrityksen, joka on julkaissut tuotteen. Tämä on GS1:n myöntämä maailmanlaajuisesti yksilöllinen tunniste.  
**5. Ilmaisinluku ja tuotenimikkeen numero**  
Arvo: ```000024```  
Kuvaus: Yhdistää ilmaisinluvun ja tuotetunnuksen.  
**6. Sarjanumero**  
Arvo: ```12345678910```  
Kuvaus: Yksilöi tuotteen jokaisen yksittäisen instanssin. Tämä mahdollistaa tuotekohtaisen seurannan.  

**Lisäosat**  
>**Jakoparametri**   
Määrittää, mihin kohtaan erotinmerkki ```( . )``` asetetaan GS1-yritystunnuksen ja tuotetunnuksen välille. Jakoparametri riippuu GS1-yritystunnuksen pituudesta. Viimeinen erotinmerkki ```( . )``` URI:ssä erottaa GTINnumeron (Global Trade Item Number) sarjanumerosta.\
>**Tarkistusnumero**  
Käytetään virheentarkistukseen GTIN-tunnuksissa. Tarkistusnumeroa ei kuitenkaan sisällytetä EPC-koodiin RFID-tunnisteessa, sillä RFID-prosessoinnissa sitä ei tarvita.  

**Käyttäjämuisti-osio**  
Muu lisätieto sijoitetaan RFID-sirun käyttäjämuisti-osioon (User memory) seuraavalla tavalla:

###### Taulukko 11. Mahdolliset lisätiedot betonielementtien käyttötapauksessa

<html>
<table>
    <thead>
        <tr>            
            <th>GS1-sovellustunnus (AI)</th>
            <th>Selite</th>
            <th>Arvo (esimerkki)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>(91) Internal</td>
            <td>Elementtitunnus</td>
            <td><code>V1001</code></td>
        </tr>
         <tr>
            <td>(92) Internal</td>
            <td>GUID</td>
            <td><code>ba34cf17-0c4b-4c6f-9295-cae05aa74ad4</code></td>
        </tr>
        <tr>
            <td>(99) Internal</td>
            <td>Verkkotunnus</td>
            <td><code>id.rt.fi</code></td>
        </tr>
     </tbody>
</table>
</html>


**RFID-tunnisteiden toteuttaminen**  
RFID-tunnisteiden ohjelmointia varten on hyvä olla yhteydessä tunnistamisen ratkaisuihin erikoistuneeseen yritykseen tai yrityksiin. Tunnistamisen ratkaisuja tarjoavia yrityksiä on koottu mm. GS1:n kumppanisivulle ja RFID Lab Finlandin ry:n sivulle.  

#### 4.1.1 RFID-tunniste symbolin käyttö  
RFID-teknologiaa käytettäessä tuotteiden automaattiseen tunnistamiseen on syytä varmistaa, että RFID-tunniste symboli sisällytetään tuote-etiketteihin sekä tuotantosuunnitelmiin. Symbolin tulee olla standardin mukainen, helposti tunnistettavissa ja sijoitettu niin, että se osoittaa selkeästi RFID-tunnisteiden sijainnin ja käytön.  


###### Taulukko 12. Yleinen RFID-symboli (ISO 7000-3010). <sup>[1]</sup> <sup>[2]</sup> <sup>[3]</sup>

<html>
    <tbody>
        <tr>
         <table>
 <th rowspan="4">
<img width="300" alt="RFID-symbol" src="https://github.com/user-attachments/assets/5c9d4d49-e5d6-4bac-a66f-c77a9731fce9"/>
               </th>
         <th>RFID-tunniste symboli</th>
        </tr>
        <tr>
            <td>RFID-tunnistesymbolina suositellaan käytettäväksi ISO 7000-3010 -standardin mukaista, vapaasti saatavilla olevaa yleistä RFID-symbolia. Symbolin käytön tulee täyttää ISO/IEC 29160:2020-standardin vaatimukset, erityisesti silloin kun symbolia hyödynnetään osoittamaan RFID-tunnisteiden sijaintia. </td>
        </tr>
        <tr>
            <th>Koko</th>
        </tr>
         <tr>
            <td>RFID-tunniste symbolin (ISO 7000-3010) tulisi olla vähintään (5 × 5) mm:n kokoinen, ja tämän ympärille tulisi jättää 1 mm:n vapaa alue. Kun RFID-tunniste symboli esitetään matalakontrastisena, sen on oltava riittävän suuri, jotta se on helposti tunnistettavissa tavanomaisissa käyttöolosuhteissa. </td>
        </tr>
    </tbody>
</table>
</html>

**Soveltaminen betonielementtien käyttöympäristössä**  
RFID-merkintä symboli on sijoitettava siten, että se näkyy helposti niille, jotka yrittävät etsiä tai lukea varsinaista RFID-tunnistetta. RFID-tunnistesymbolin käyttöä suositellaan betonielementtien tuotantosuunnitelmissa osoittamaan RFID-tunnisteiden sijaintia (esimerkki kuvattu liitteessä 1). RFID-tunnisteen käyttö tulee merkitä RFID-tunniste symbolin avulla, ja käytettävä tunnistetyyppi sekä sijaintitiedot lisätään osaksi betonielementin tuoteosaluetteloa.

**RFID-tunnisteen sijoittaminen fyysiseen tuotteeseen**  
RFID-merkittyjen objektien luettavuuteen vaikuttavat useat tekijät, kuten RFID-siru, RFID-antenni ja kotelointi (koko RFID-tunniste). Lisäksi ympäristö, jossa RFID-tunniste luetaan, vaikuttaa olennaisesti luettavuuteen. Ympäristö, jossa on paljon metalliesineitä, voi esimerkiksi aiheuttaa ei-toivottuja heijastuksia radioaaltoihin, jolloin luenta vaikeutuu tai luetaan väärä kohde.

Markkinoilla on erilaisia RFID-tunnisteita, jotka soveltuvat eri käyttötarkoituksiin. RFID-tunnisteita voidaan käyttää betonielementtien toimintaympäristössä betonielementtien sisään valettuna, elementtien pinnalla, tai osana betonielementteihin kiinnitettävää tuote-etikettiä. Betonielementtiin valettaessa, RFID-tunnisteen luettavuuteen vaikuttaa sen ympärillä oleva materiaali, joten valittavan RFID-tunnisteiden tulee olla sellainen, että se on luettavissa sitä ympäröivän betonin läpi riittävästä syvyydestä. Ulkoisessa aplikaattorilla muodostetussa tuoteetiketissä tulee olla merkintä RFID-tunnisteen käytöstä sekä tarkennus siitä, sijaitseeko tunniste itse lapussa vai valettuna elementin sisällä. RFID:n käytön hyödyt perustuvat automatisoituihin lukutapahtumiin ja niistä syntyvään tapahtumatietoon. Lukutapahtumalla tarkoitetaan yksinkertaistettuna sitä, että lukijalaite havaitsee tietyn RFID-tunnisteen.

### 4.2 Tuotetunnistus GS1 DataMatrix 2D-koodilla
GS1 DataMatrix on GS1:n kehittämä kaksiulotteinen viivakoodi, joka voidaan tulostaa yksittäisistä pisteistä tai neliöistä koostuvana neliön tai suorakaiteen muotoisena symbolina. GS1 DataMatrix voi sisältää perinteistä lineaarista viivakoodia suuremman määrän tietoa. Siihen on mahdollista koodata jopa 3116 numeerista merkkiä tai 2335 alfanumeerista merkkiä. GS1 sovellustunnusten avulla GS1 DataMatrixiin voidaan sisällyttää useita erityyppisiä tietoja, kuten esimerkiksi määritetyt betonielementtien minimitietovaatimukset. GS1 DataMatrixin lukeminen vaatii kamerapohjaisen skannerin.

###### Taulukko 13. Esimerkki betonielementtien minimitietovaatimukset sisältävästä GS1 DataMatrix -koodista

<html>
<table>
   <tbody>
         <tr>  
         <th rowspan="7"><img width="110" alt="2025-06-23_Kuva2" src="https://github.com/user-attachments/assets/ce285bc2-6cfd-4abf-80c2-090c914afd56" />
         </th>   
         <th colspan="2">Esimerkin tietosisältö</th>
        </tr>
         <tr>
            <td><b>GS1-sovellustunnus (AI)</b></td>
            <td><b>Arvo (esimerkki)</b></td>
        </tr>
        <tr>
            <td>(01) = GTIN</td>
            <td><code>06400001000247</code></td>
        </tr>
         <tr>
            <td>(242) = MTO variation number</td>
          <td><code>123456</code></td>
        </tr>
        <tr>
            <td>(21) = Serial number</td>
            <td><code>12345678910</code></td>
        </tr>
       <tr>
            <td>(91) = Internal (elementtitunnus)</td>
            <td><code>V1001</code></td>
        </tr>
       <tr>
            <td>(92) = Internal (GUID)</td>
            <td><code>ba34cf17-0c4b-4c6f-9295-cae05aa74ad4</code></td>
        </tr>
    </tbody>
</table>
</html>

**GS1 DataMatrix -tunnisteen koko ja laatu**   
Viivakoodin fyysinen koko vaihtelee sen sisältämän tiedon määrän mukaan. Viivakoodin resoluution (X-dimensio) on oltava vähintään 0,38 mm ja enintään 0,45 mm. Merkinnöissä käytettävien GS1 2D-viivakoodien laadun tulee täyttää ISO / IEC 15415 -standardin vaatimukset. Näin voidaan varmistua niiden luettavuudesta.  
Merkintöjen tulostamista varten on hyvä olla yhteydessä tunnistamisen ratkaisuihin erikoistuneeseen yritykseen tai yrityksiin. Tunnistamisen ratkaisuja tarjoavia yrityksiä on koottu mm. GS1:n kumppanisivulle.

## 4.3 Tuotetunnistus GS1 Digital Link -standardin mukaisella QR-koodilla
Mikäli tunnisteen avulla halutaan yksilöinnin ja tunnistamisen lisäksi viestiä kuluttajalle/käyttäjälle älypuhelimen tai muun vastaavan laitteen kautta, voidaan tunnisteena käyttää GS1 Digital Link -standardin mukaista QR-koodia. Tavallisesta QR-koodista tämä eroaa siten, että sen tietosisältö on GS1-standardin määrittämä. Standardi varmistaa, että koodit ja niiden sisältämät tiedot ovat rakenteeltaan yhdenmukaisia ja siten liikuteltavia eri järjestelmien ja toimijoiden välillä sekä luettavissa ja tulkittavissa viivakoodinlukijoilla.

GS1 Digital Link URI:n sisältävä QR-koodi palvelee kahta käyttötarkoitusta:

>**1. Tuotteen yksilöinti ja tunnistaminen offline-tilassa**  
Sitä voidaan käyttää ilman verkkoyhteyttä tuotteen yksilöimiseen ja tunnistamiseen viivakoodinlukijoilla, aivan kuten perinteisiä EAN-viivakoodeja. Tuotteen yksilöinnissä käytetään QR-koodiin sisällytettävää GS1-standardin mukaista GTIN-koodia ja tarvittavia lisätietoja, kuten MTO varianttinumeroa ja sarjanumeroa.

>**2. Verkossa jaettava tietosisältö**  
Sitä voidaan käyttää kuten mitä tahansa QR-koodia, eli ohjaamaan älypuhelimen tai muun vastaavan laitteen käyttäjä verkossa olevaan sisältöön. Erilaiset sovellukset voivat suorittaa saman QR-koodin lukemisen kautta myös muita toimintoja ja näyttää erilaista sisältöä.

GS1 Digital Link URI:ssa käytetään GS1-sovellustunnuksia tietojen sisällyttämiseen. Alla olevassa esimerkissä on muodostettu taulukossa esitetyt minimitietovaatimukset sisältävä GS1 Digital Link URI.

###### Taulukko 14. Esimerkin QR-koodi sisältää taulukossa esitetyt tiedot GS1 Digital Link URI -muodossa: https://id.rt.fi/01/06400001000247/242/123456/21/12345678910

<html>
<table>
    <tbody>
        <tr>            
          <th rowspan="5"><img width="110" alt="QR-koodi_Kuva1" src="https://github.com/user-attachments/assets/22a88262-4a5f-469a-bd88-95fa37559281" />
            </th>   
         <th colspan="2">Esimerkin tietosisältö</th>
        </tr>
        <tr>
            <td><b>GS1-sovellustunnukset (AI)</b></td>
            <td><b>Arvo (esimerkki)</b></td>
        </tr>
        <tr>
            <td>(01) = GTIN-koodi</td>
            <td><code>06400001000247</code></td>
        </tr>
         <tr>
            <td>(242) = MTO variation number</td>
          <td><code>123456</code></td>
        </tr>
        <tr>
            <td>(21) = Serial number</td>
            <td><code> 12345678910</code> </td>
        </tr>
    </tbody>
</table>
</html>

**Esimerkki GS1 Digital Link QR-koodien käyttötarkoituksesta ja suosituksista**  
Esimerkin tarkoitus on ainoastaan esitellä tietosisällön rakennetta. Siinä on käytetty kuvitteellista verkkotunnusta id.rt.fi, joten älypuhelimen kameralla luettaessa esimerkkikoodi ei ohjaudu mihinkään sisältöön.  

Lähtökohtaisesti suositellaan, että QR-koodiin sisällytetyn GS1 Digital Link URI:n ei tulisi olla minkään varsinaisen verkkosivun URL-osoite. Tästä osoitteesta suositellaan tekemään uudelleenohjaus siihen sisältöön, joka koodin kautta halutaan näyttää.  

GS1 Digital Link URI:ssa voidaan käyttää mitä tahansa verkkotunnusta, koska se ei vaikuta tuotteen yksilöintiin ja tunnistamiseen. Verkkotunnus määrittää, minne QR-koodin skannaava henkilö ohjataan verkossa. Koodissa on siten mahdollista käyttää myös palveluntarjoajan verkkotunnusta, mutta on hyvä tiedostaa, että tästä voi seurata ns. vendor lock-in -tilanne, jolloin palveluntarjoajan vaihtaminen vaatii verkkotunnuksen muutoksen myötä myös tuotteisiin painettujen koodien vaihtamisen. Siksi on suositeltavaa käyttää koodissa yrityksen omaa verkkotunnusta. Näin tehdessään yritys voi edelleen ohjata sen tarvittaessa uudelleen palveluntarjoajan verkkotunnuksen alla olevaan sisältöön, jos sille koetaan tarvetta.  

**Suositeltu lähestymistapa: Tuotteen tunnistamiseen käytettävän aladomainin käyttö**  
Suositeltu toimintapa on käyttää GS1 Digital Link -standardin mukaisessa QR-koodissa varsinaisen verkkotunnuksen alle luotavaa, tuotteiden yksilöintitarpeisiin varattua aliverkkotunnusta. Aliverkkotunnus (alidomain) on varsinaisesta verkkotunnuksesta irrallinen osio, jota käytetään varsinaisen verkkotunnuksen rinnalla johonkin tiettyyn käyttötarkoitukseen. Aliverkkotunnuksen käyttö QR-koodissa mahdollistaa tuoteyksilöinnissä käytettävien URL-osoitteiden pysyvyyden ja riippumattomuuden varsinaisten verkkosivujen rakenteesta. Tämä tuo joustavuutta yrityksen verkkosivujen ylläpitoon, koska päivitysten yhteydessä ei tarvitse huolehtia QR-koodissa olevasta linkistä, vaan koodista voidaan aina tehdä uudelleenohjaus päivitettyyn kohdesivustoon.  

**Esimerkkejä aliverkkotunnuksen käytöstä**  
Aliverkkotunnus voidaan tehdä joko yrityksen verkkotunnuksen tai sen eri brändien verkkotunnusten perusteella.  
Esimerkiksi:  

```yritys-x.fi``` -> ```id. yritys-x.fi```  

```brand-x.fi``` -> ```id.brand-x.fi```  

Mitä lyhyempi GS1 Digital Link URI on, sitä pienempään tilaan sen sisältävä QR-koodi mahtuu.  
GS1 Digital Link -standardin käyttöä on kuvattu tarkemmin seuraavissa GS1-standardeissa:  
https://ref.gs1.org/standards/digital-link/uri-syntax/  
https://ref.gs1.org/standards/resolver/

## Lyhenteet ja terminologia
|**Nimike**|**Selite**|
|-----------|---------------|
|Aplikaattori | Laite, joka tulostaa ja kiinnittää RFID-tunnisteen tuotteeseen|
Electronic Product Code, EPC | Sähköinen tuotekoodi. <sup>[7]</sup>
EPC-muisti  | RFID-tunnisteen muisti, johon sähköinen tuotekoodi kirjoitetaan, eli tunnisteen perusmuisti
Engineer-To-Order, ETO  | Termillä tarkoitetaan tilauksesta suunniteltavien tuotteiden valmistuslogiikkaa.
GS1 DataMatrix  | GS1-standardin mukainen 2D-koodi, johon voidaan sisällyttää enemmän tietoa kuin perinteiseen EAN-viivakoodiin. ISO/IEC 16022
GS1 Application Identifier, AI  | GS1-sovellustunnukset ovat 2–4 numeron pituisia tunnuksia, joita käytetään GS1-128-, GS1 DataMatrix- ja GS1 DataBar -viivakoodeissa sekä EPC/RFID-tunnisteissa.
Global Trade Item Number, GTIN  | Termillä tarkoitetaan GS1:n tuotetunniste standardia. <sup>[8]</sup> <sup>[9]</sup>
GUID  | GUID (Globally Unique IDentifier) on mallinnusohjelman antama tai muulla tavalla luotu kullekin osalle yksilöllinen tunniste. Kulkee myös nimellä UUID (Universally Unique IDentifier). <sup>[10]</sup> <sup>[11]</sup>
Make-To-Order, MTO | Termi tarkoittaa tilausohjautuvaa tuotantoa, jossa tuotteet valmistetaan asiakastilausten mukaisesti valmiiden tuotesuunnitelmien pohjalta.
Make-To-Stock, MTS | Termillä tarkoitetaan varasto-ohjautuvien tuotteiden valmistuslogiikkaa.
Radio Frequency Identificatio, RFID  | Termillä tarkoitetaan radiotaajuisia etätunnisteita (sisältää antennin ja mikropiirin).
Serial Global Trade Item Number, SGTIN  | GTIN-koodin ja sarjanumeron yhdistelmä, jolla voidaan erottaa identtiset tuoteyksilöt toisistaan.
Tag | RFID-tunniste, joka sisältää sirun ja antennin. Käytetään objektien yksilölliseen tunnistamiseen.
User memory  | RFID käyttäjämuisti tai lisämuisti
UHF tunniste | Korkeataajuinen (850–960 MHZ) RFID tunniste
Uniform Resource Identifier, URI  | URI on tietoverkossa sijaitsevan tiedon tunniste. URL on aina myös URI, mutta URI ei välttämättä ole URL. Esimerkiksi <code>https://rt.fi</code> tai <code>urn:ISBN:952-9842-34-1</code>
Uniform Resource Locator, URL  | URL sisältää tiedon hakemiseen tarvittavan tiedon, kuten protokollan (esim. https) ja palvelimen. Esimerkiksi <code>https://rt.fi</code>
Verkkotunnus | Verkkotunnus eli domain-nimi on merkkijono, joka ohjataan internetissä tiettyyn IP-osoitteeseen eli palvelimelle. Esimerkiksi <code>www.iso.org</code>

## Viittaukset
**[1]** GS1 (2022), Recommendation for the use of EPC and ISO RFID symbols   

**[2]** ISO/IEC 29160:2020, Information technology — Radio frequency identification. Saatavilla:https://www.iso.org  

**[3]** ISO 7000-3010:2020, RFID-tag. Saatavilla:https://www.iso.org/obp/ui#iso:grs:7000:3010 

**[4]** GS1 (2023), GTIN Management Guideline for Construction Products. Saatavilla:https://www.gs1.org/standards/gtin-management-guideline-construction-products/current-standard#2-GTIN-Management-Rule-examples-for-construction-products+2-2-Declared-formulation-or-functionality.  

**[5]** GS1 (2024), GS1 Application Identifiers. Saatavilla: https://ref.gs1.org/ai/. 

**[6]** GS1 Norway (2018), Guideline for Unique identification of products with SGTIN (serialized GTIN). Labelling with GS1Datamatrix barcode and tagging with EPC / RFID Gen 2 UHF RFID tags. 

**[7]** ISO/IEC 15962:2022, EPC Tag Data Standard. Saatavilla: https://ref.gs1.org/ai/. 

**[8]** ISO/IEC 15459-6:2014 - Unique identification

**[9]** ISO/IEC 6523-1:2023: - Information technology – Structure for the identification of organizations and organization parts

**[10]** ISO/IEC 11578:1996 Information technology - Open Systems Interconnection - Remote Procedure Call (RPC)

**[11]** ISO/IEC 9834-8:2014 - Information technology

## Liite 1
![20250109_BETK Soveltamisohje_Tuoteyksilöinti ja -tunnistaminen (1)_1](https://github.com/user-attachments/assets/a815804d-46ae-49bf-bf53-827eaab8e0c9)
