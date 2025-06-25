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

Precast concrete elements are inherently Make-To-Order (MTO) and Engineer-To-Order (ETO) products, meaning their identification using GTIN codes differs fundamentally from that of Make-To-Stock (MTS) products. While it is possible to assign a unique GTIN code to each individual precast element, the BETK working group has opted to use the GS1 standard with a three-level identification model (as shown in Figure 1). In this model the GTIN code identifies a specific base product type from a specific manufacturer. The Made-To-Order (MTO) variant number distinguishes a particular variant of the base product. The serial number uniquely identifies identical units of the same variant.

Thus, a GTIN alone does not uniquely identify a specific product but rather represents a general category of possible product variations that may be manufactured based on the order.

![2025-06-23_Kuva3](https://github.com/user-attachments/assets/9fa68e30-01da-458f-8cb4-9c80be84a9bb)

###### Figure 1.  Hierarchical levels of product identification for more precise identification

### 3.1 Using GS1 application identifiers to identify ETO products  
GS1 Application Identifiers (AI) are numeric prefixes used in barcodes and EPC/RFID tags to define the meaning and format of data elements. The use of AIs enables the differentiation of various data elements within barcodes or EPC/RFID tags. The GS1 standard includes over 100 application identifiers. Each AI is typically a two-, three-, or four-digit number. A comprehensive list of all GS1 Application Identifiers is available on the GS1 website:https://ref.gs1.org/ai/.

The following GS1 Application Identifiers (AIs) have been identified as necessary to meet the minimum data requirements for the identification of precast concrete elements:  
• ```(01) GTIN```: Global Trade Item Number – identifies the base product type.  
• ```(242) Made-to-Order Variation Number```: Distinguishes a specific variant of the base product.  
• ```(21) Serial Number```: Uniquely identifies individual units of the same variant.  

The GS1 standard does not currently provide specific GS1 Application Identifiers (AIs) for the National Element Classification number, GUID, or Domain Name. Therefore, the BETK project has decided to use the following application identifiers for including this data in information carriers:  
• ```(91) Company Internal Information```  
• ```(92) Company Internal Information```  
• ```(99) Company Internal Information```  

GS1 AIs starting with the digit 9 are reserved for company-specific or internal use and should only be applied when there is no official GS1 Application Identifier defined for the particular data element. This approach ensures flexibility while adhering to GS1 standards for data structuring.

Note! At the time of this guideline's publication, the handling of domain names in RFID tags is under review within GS1's international standard development process. The forthcoming standard may differ from the solution presented here, and this guidance will be updated accordingly once the standard is finalized.

For optical recognition (e.g., QR codes), the inclusion of this information follows the procedure outlined in the GS1 Digital Link URI Syntax 1.5.0 standard.

###### Table 1. Minimum data requirements to be included in the information carrier (2D DataMatrix Barcode or EPC/RFID Tag)

| GS1 Application Identifier (AI) | Example                      |
|---------------------------------|------------------------------|
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

###### Table 10. Applicable Method: SGTIN-96. The SGTIN-96 encoding method is commonly used. However, the TDS 2.1 (EPC Tag Data Standard) also includes other encoding methods, such as SGTIN-198, which can be utilized if there is a need for longer serial numbers or serial numbers that include both letters and numbers.

<html>
<table>
    <thead>
        <tr>             
         <th colspan="3">Data structure SGTIN-96</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>EPC SGTIN-96</b></td>
            <td><b>Value</b></td>
            <td><b>Comment</b></td>
        </tr>
        <tr>
            <td>Header</td>
            <td><code>48</code></td>
            <td>Number for SGTIN-96</td>
        </tr>
      <tr>
            <td>Filter value</td>
            <td><code>0</code></td>
            <td>0 = Applicable Value for a Product Not Scanned at Point-of-Sale</td>
        </tr>
         <tr>
            <td rowspan="6">Partition</td>
            <td rowspan="6"><code>1</code>,<code>2</code>,<code>3</code>,<code>4</code>,<code>5</code>or<code>6</code></td>
            <td>
              1 = GS1 GCP of 11 digits and 2 digits in item number + indicator                                        
            </td>
        </tr>
        <tr>
            <td>2 = GS1 GCP of 10 digits and 3 digits in item number + indicator </td>
        </tr>
       <tr>
            <td>3 = GS1 GCP of 9 digits and 4 digits in item number + indicator</td>
        </tr>
       <tr>
            <td>4 = GS1 GCP of 8 digits and 5 digits in item number + indicator</td>
        </tr>
        <tr>
            <td>5 = GS1 GCP of 7 digits and 6 digits in item number + indicator</td>
        </tr>
        <tr>
            <td> 6 = GS1 GCP of 6 digits and 7 digits in item number + indicator</td>
        </tr>
         <tr>
          <td>GS1 Company Prefix (GS1 GCP)</td>
          <td><code>N…11</code></td>
          <td>GS1 GCP: 6,7,8,9,10 or 11 digits</td>
         </tr>
        <tr>
          <td>Item number</td>
          <td><code>N…7</code></td>
          <td>Depending on the number of digits in GS1 GCP. 1–7 digits</td>
        </tr>
         <tr>
          <td>Serial number </td>
          <td><code>N…12</code></td>
          <td>Up to 12 digits (hiqhest allowable value = 274 877 906 943) A fixed number of digits is chosen for serial number, it must not be 12 digits. You choose as many as needed. Leading zero is not allowed</td>
        </tr>
    </tbody>
</table>
</html>

**Example of data string in an EPC / Gen2 RFID chip**  
RFID Tag EPC Memory Bank Contents (hexadecimal): ```301586A004000602DFDC1C3E```  
EPC Tag URI: ```urn:epc:tag:sgtin-96:0.6400001.000024.12345678910```  

**Data Structure Breakdown**  
**1. URN Prefix**  
Value: ```urn:epc:id```  
Description: Specifies that this is a Uniform Resource Identifier (URI).  
**2. EPC Scheme**  
Value: ```sgtin-96```  
Description: Indicates the GS1 Identification Key used in this case (Serialized Global Trade Item Number with 96-bit encoding).  
**3. Filter Value**  
Value: ```0```  
Description: Filter value indicating "product not scanned at the point-of-sale."  
**4. GS1 Company Prefix**  
Value: ```6400001```  
Description: Identifies the company issuing the product. 
**5. Indicator and Item Reference Number**  
Value: ```000024```  
Description: Combines the indicator digit and the item reference number for the specific product.  
**6. Serial Number**  
Value: ```12345678910```  
Description: Uniquely identifies the specific instance of the product.  

**Additional Notes**  
>**Partition Value**   
Determines where the separator ```( . )``` is placed to divide the GS1 Company Prefix and the Item Reference
Number. The last separator ```( . )``` in the URI distinguishes the GTIN (Global Trade Item Number) from the
serial number.\  

>**Check Digit**  
Not included in the EPC code stored in the RFID tag.\  

**User Memory Section**
Additional information can be stored in the User Memory of the RFID chip as Application Identifiers (AIs):

###### Table 11. Additional information on the use of concrete elements

<html>
<table>
    <thead>
        <tr>            
            <th>GS1 Application Identifier (AI)</th>
            <th>Definition</th>
            <th>Value (example)</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>(91) Internal</td>
            <td>Element classification</td>
            <td><code>V1001</code></td>
        </tr>
         <tr>
            <td>(92) Internal</td>
            <td>GUID</td>
            <td><code>ba34cf17-0c4b-4c6f-9295-cae05aa74ad4</code></td>
        </tr>
        <tr>
            <td>(99) Internal</td>
            <td>Domain name</td>
            <td><code>id.rt.fi</code></td>
        </tr>
     </tbody>
</table>
</html>

**Implementing RFID Tags**
For programming RFID tags, it is recommended to collaborate with companies specializing in identification solutions. A list of such solution providers can be found on the GS1 Partner Page and the RFID Lab Finland Association website.

#### 4.1.1 Use of RFID symbol
When using RFID technology for automatic product identification, it is essential to ensure that the RFID tag symbol is included on product labels and production plans. The symbol must comply with standards, be easily recognizable, and be positioned in a way that clearly indicates the location and use of RFID tags.

###### Table 12. General RFID symbol (ISO 7000-3010). <sup>[1]</sup> <sup>[2]</sup> <sup>[3]</sup>

<html>
    <tbody>
        <tr>
         <table>
 <th rowspan="4">
<img width="300" alt="RFID-symbol" src="https://github.com/user-attachments/assets/5c9d4d49-e5d6-4bac-a66f-c77a9731fce9"/>
               </th>
         <th>RFID symbol</th>
        </tr>
        <tr>
            <td>The ISO 7000-3010 standard's freely available general RFID symbol is recommended for use as the RFID tag symbol. The use of this symbol must comply with the requirements of the ISO/IEC 29160:2020 standard, especially when the symbol is used to indicate the location of RFID tags.  </td>
        </tr>
        <tr>
            <th>Size</th>
        </tr>
         <tr>
            <td>The RFID tag symbol (ISO 7000-3010) should have a minimum size of 5 × 5 mm, with a 1 mm clear zone surrounding it. When the RFID tag symbol is presented in low contrast, it must be sufficiently large to ensure it is easily recognizable under typical operating conditions. </td>
        </tr>
    </tbody>
</table>
</html>

**Utilizing RFID Symbols on Precast Concrete Elements**  
The RFID symbol must be positioned so that it is easily visible to those trying to locate or read the actual RFID tag. The use of an RFID symbol is recommended in precast concrete production drawings to indicate the location of RFID tags (example illustrated in Annex 1). The use of the RFID tag shall be indicated by the RFID tag symbol and the type of tag used and the location information shall be included in the product catalogue of the precast concrete element.

**Placing the RFID Tag to the Physical Product**
The readability of RFID tagged objects is affected by several factors, such as the RFID chip, the RFID antenna and the encapsulation (the whole RFID tag). The environment in which the RFID tag is read has a significant impact on readability. For example, an environment with many metal objects can detune and reflect RFID signals, while liquids tend to absorb them, both of which can interfere with the performance of RFID systems.

There are different types of RFID tags on the market, suitable for different uses. RFID tags can be used in a precast concrete environment, embedded in the precast concrete, on the surface of the precast concrete, or as part of a product label to be attached to precast concrete. When cast into a precast concrete element, the readability of the RFID tag is affected by the material surrounding it, so the RFID tag chosen should be such that it can be read through the surrounding concrete to a sufficient depth. The product label formed by the external applicator should include a note on the use of the RFID tag and a specification as to whether the tag is located on the tab itself or cast inside the element. The benefits of using RFID are based on automated reading events and the resulting transaction path. In simple terms, a read event is when a reader detects a specific RFID tag.


### 4.2 GS1 DataMatrix barcode
GS1 DataMatrix is a two-dimensional barcode developed by GS1 that can be printed as a square or rectangular symbol consisting of individual dots or squares. The GS1 DataMatrix can contain a larger amount of data than a traditional linear barcode. Up to 3116 numeric characters or 2335 alphanumeric characters can be encoded. GS1 application codes allow the GS1 DataMatrix to include many different types of data, such as minimum data requirements for specified concrete elements. A camera-based scanner is required to read the GS1 DataMatrix.

###### Table 13. Example of a GS1 DataMatrix code containing information requirements for precast concrete elements

<html>
<table>
   <tbody>
         <tr>  
         <th rowspan="7"><img width="110" alt="2025-06-23_Kuva2" src="https://github.com/user-attachments/assets/ce285bc2-6cfd-4abf-80c2-090c914afd56" />
         </th>   
         <th colspan="2">Example information content</th>
        </tr>
         <tr>
            <td><b>GS1 Application Identifier (AI)</b></td>
            <td><b>Value (example)</b></td>
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
            <td>(91) = Internal (element classification)</td>
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
The physical size of a barcode varies according to the amount of data it contains. The resolution (X-dimension) of the barcode shall be a minimum of 0,38 mm and a maximum of 0,45 mm. The quality of the GS1 2D barcodes used for marking shall meet the requirements of ISO/IEC 15415. This will ensure their legibility.

It is advisable to contact a company or companies specialising in identification solutions for the printing of the markings. Companies offering identification solutions are listed on the GS1 partner page.

### 4.3 GS1 Digital Link QR code  
If the tag is intended to not only enable identification and carry data but also communicate with the consumer/user via a smartphone or similar device, a QR code compliant with the GS1 Digital Link standard can be used. Unlike a regular QR code, the data content of this code is defined by the GS1 standard. The standard ensures that the codes and the information they contain are structurally consistent, making them interoperable across different systems and stakeholders, as well as readable and interpretable by barcode scanners.

A QR code containing a GS1 Digital Link URI serves two purposes: 

>**1. Offline Product Identification and data capture**
It can be used without an internet connection to identify and data capture the product via barcode scanners, just like traditional EAN barcodes. The product is identified using the GTIN code included in the QR code, as specified by the GS1 standard, along with additional required information such as the MTO variation number and serial number.

>**2. Online Interaction**
It can be used like any other QR code to direct the user of a smartphone or similar device to online content. Various applications can also perform other actions and display different content based on the same QR code scan.

The GS1 Digital Link URI incorporates GS1 Application Identifiers for embedding data. The example below shows
a GS1 Digital Link URI formed to include the minimum data requirements presented in the table

###### Table 14. The QR code in the example contains the information shown in the table in GS1 Digital Link URI format:
: https://id.rt.fi/01/06400001000247/242/123456/21/12345678910

<html>
<table>
    <tbody>
        <tr>            
          <th rowspan="5"><img width="110" alt="QR-koodi_Kuva1" src="https://github.com/user-attachments/assets/22a88262-4a5f-469a-bd88-95fa37559281" />
            </th>   
         <th colspan="2">Example information content</th>
        </tr>
        <tr>
            <td><b>GS1 Application Identifier (AI)</b></td>
            <td><b>Value (example)</b></td>
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
            <td><code> 12345678910</code> </td>
        </tr>
    </tbody>
</table>
</html>

**Example Purpose and Recommendations for GS1 Digital Link QR Codes**
The purpose of the example is solely to demonstrate the structure of the data content. It uses a fictional Domain Name <code>id.rt.fi</code>, so when scanned with a smartphone camera, the example code does not direct to any actual content. 

As a general recommendation, the GS1 Digital Link URI included in the QR code should not point directly to a live webpage's URL. Instead, it is recommended to set up a redirection from this address to the desired content to be displayed through the code.

The Domain Name in a GS1 Digital Link URI can be any Domain Name, as it does not affect the product's identification or recognition. The Domain Name determines where the person scanning the QR code will be directed online. Therefore, it is possible to use the Domain Name of a service provider in the code. However, it is important to be aware that this may lead to a vendor lock-in situation, where changing the service provider would require replacing the codes printed on the products due to the change in the Domain Name.

**Recommended Approach: Using a Subdomain for Product Identification**
It is recommended to use the company's own Domain Name in the QR code. This allows the company to redirect it, if needed, to content hosted under the service provider's Domain Name. A preferred practice is to create a dedicated Subdomain under the main Domain Name for product identification purposes.

A Subdomain is a separate section of the main Domain Name, used alongside the main domain for specific purposes. Using a Subdomain in QR codes ensures the permanence and independence of the URLs used for product identification from the structure of the main website. This approach adds flexibility to the maintenance of the company's website, as updates to the main website do not require changes to the links embedded in the QR codes. The codes can always be redirected to the updated target pages.

**Examples of Subdomain Usage**
The Subdomain can be based on the company's main domain or its various brand domains.  
For example:

```company-x.fi``` -> ```id.company-x.fi```  

```brand-x.fi``` -> ```id.brand-x.fi```  

The shorter the GS1 Digital Link URI, the smaller the QR code containing it can be.

**Further Information**
The use of the GS1 Digital Link standard is described in greater detail in the following GS1 standards:  
https://ref.gs1.org/standards/digital-link/uri-syntax/  
https://ref.gs1.org/standards/resolver/

## Terms and definitions

<html>
<table>
    <tbody>
        <tr>            
          <td>Applicator</td>
          <td>A device that prints and applies an RFID tag to a product</td>
        </tr>
        <tr>
           <td>Electronic Product Code, EPC</td>
          <td>See EPC Tag Data Standard ISO/IEC 15962 <sup>[7]</sup></td>
        </tr>
        <tr>
          <td>EPC-memory</td>
          <td>The memory of an RFID tag where the EPC is written, serving as the tag's primary memory</td>
        </tr>
         <tr>
          <td>Engineer-To-Order, ETO </td>
          <td>Engineer-To-Order (ETO) refers to a manufacturing logic where products are designed and engineered to meet specific customer orders</td>
        </tr>
        <tr>
          <td>GS1 DataMatrix</td>
          <td>A GS1-compliant 2D code that can encode more information than a traditional EAN barcode. Complies with ISO/IEC 16022</td>
        </tr>
           <tr>
          <td>GS1 Application Identifier, AI</td>
          <td>GS1 Application Identifiers (AI) are 2- to 4-digit codes used in GS1-128, GS1 DataMatrix, and GS1 DataBar barcodes, as well as in EPC/RFID tags</td>
        </tr>
         <tr>
          <td>Global Trade Item Number, GTIN</td>
          <td>Global Trade Item Number (GTIN) is a GS1 product identification standard. <sup>[8]</sup> <sup>[9]</sup></td>
        </tr>
        <tr>
          <td>GUID</td>
          <td>Globally Unique Identifier (GUID) is a unique identifier assigned to each part by a modeling program or generated by other means. It is also known as a Universally Unique Identifier (UUID). <sup>[10]</sup> <sup>[11]</sup></td>
        </tr>
           <tr>
          <td>Make-To-Order, MTO</td>
          <td>Make-To-Order or Made-To-Order (MTO) refers to demand-driven production where products are manufactured based on customer orders, using predefined product designs</td>
        </tr>
         <tr>
          <td>Radio Frequency Identificatio, RFID</td>
          <td>Automatic Identification and Data Capture (AIDC) carrier that consists of a microchip, which stores and processes data, and an antenna, which transmits and receives signals</td>
        </tr>
        <tr>
          <td>Serial Global Trade Item Number, SGTIN</td>
          <td>A combination of a GTIN code and a serial number that allows identical product units to be distinguished from one another</td>
        </tr>
     <tr>
          <td>User memory</td>
          <td>A section of an RFID tag's memory that can be used to store additional, user-defined data beyond the standard identification information. This memory is typically writable and customizable to meet specific application needs</td>
        </tr>
     <tr>
          <td>UHF Tag</td>
          <td>Ultra-high-frequency RFID tag operating within the 850–960 MHz range, commonly used for longrange and high-speed data transfer applications</td>
        </tr>
     <tr>
          <td>Uniform Resource Identifier, URI</td>
          <td>is an identifier for information located on a network. A URL is always a URI, but a URI is not necessarily a URL. For example: <code>https://rt.fi</code> tai <code>urn:ISBN:952-9842-34-1</code></td>
        </tr>
     <tr>
          <td>Uniform Resource Locator, URL</td>
          <td>URL  includes the necessary information for retrieving the resource, such as the protocol (e.g., HTTPS) and the server. For example: <code>https://rt.fi</code></td>
        </tr>
     <tr>
          <td>Domain Name</td>
          <td>A domain name is a string of characters that is mapped to a specific IP address or server on the internet. For example: <code>www.iso.org</code></td>
        </tr>
    </tbody>
</table>
</html>


## References
**[1]** GS1 (2022), Recommendation for the use of EPC and ISO RFID symbols   

**[2]** ISO/IEC 29160:2020, Information technology — Radio frequency identification. Available: https://www.iso.org  

**[3]** ISO 7000-3010:2020, RFID-tag. Available: https://www.iso.org/obp/ui#iso:grs:7000:3010 

**[4]** GS1 (2023), GTIN Management Guideline for Construction Products. Available: https://www.gs1.org/standards/gtin-management-guideline-construction-products/current-standard#2-GTIN-Management-Rule-examples-for-construction-products+2-2-Declared-formulation-or-functionality.  

**[5]** GS1 (2024), GS1 Application Identifiers. Available: https://ref.gs1.org/ai/. 

**[6]** GS1 Norway (2018), Guideline for Unique identification of products with SGTIN (serialized GTIN). Labelling with GS1Datamatrix barcode and tagging with EPC / RFID Gen 2 UHF RFID tags. 

**[7]** ISO/IEC 15962:2022, EPC Tag Data Standard. Available: https://ref.gs1.org/ai/. 

**[8]** ISO/IEC 15459-6:2014 - Unique identification

**[9]** ISO/IEC 6523-1:2023: - Information technology – Structure for the identification of organizations and organization parts

**[10]** ISO/IEC 11578:1996 Information technology - Open Systems Interconnection - Remote Procedure Call (RPC)

**[11]** ISO/IEC 9834-8:2014 - Information technology

## Annex 1
![20250109_BETK Soveltamisohje_Tuoteyksilöinti ja -tunnistaminen (1)_1](https://github.com/user-attachments/assets/a815804d-46ae-49bf-bf53-827eaab8e0c9)
