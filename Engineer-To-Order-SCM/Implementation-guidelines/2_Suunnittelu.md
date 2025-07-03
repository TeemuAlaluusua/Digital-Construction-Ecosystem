# BETK soveltamisohje: Tarjousvaiheen tietomääritykset ja toteutusvaiheen tietomalliohjeita toimitusketjulle

**Tilauksesta suunniteltavat rakennustuotteet**  
>Julkaisija: Rakennusteollisuus ry\
>Päivämäärä: 4.7.2025  
Versio: 1.3  
Status: Luonnos



## Asiakirjan tiedot
<details> 
<Summary>Asiakirjan versio</Summary>
 
| **Versio **| **Päivämäärä    **| **Tekijä**      |**Muutoskuvaus     **                           |
|------------|-------------------|-----------------|------------------------------------------------|
| 0.1        | 2024-12-30        |TAla             | Asiakirjan luonnos                             |
| 0.2        | 2025-02-25        |anpekk           | Tekstiosuuksia täydennetty                     |
| 0.3        | 2025-01-09        |anpekk           | Tekstiosuuksia täydennetty                     |
| 0.4        | 2025-06-17        |anpekk           | NCC ja Consoliksen kommentit huomioitu         |
</details>

<details> 
<Summary>Asiakirjan laatijat</Summary>

| **Nimi**            | **Organisaatio**               |
|---------------------|--------------------------------|
| Antti Pekkala       | Fira Oy                        |
| Teemu Anttila       | Ramboll                        |
| Janne Kihula        | Rakennustuoteteollisuus RTT ry |
| Teemu Alaluusua     | Aalto-yliopisto                |
| Tom Partanen        | Consolis Parma Oy              |
| Eetu Lahtinen       | Consolis Parma Oy              |
| Satu Parikka        | Consolis Parma Oy              |
| Kari Turunen        | Lujabetoni Oy                  |
| Markku Räisänen     | Betset Oy                      |
| Jarkko Vitikainen   | Sitowise Oy                    |
| Antti Taskinen      | Fira Oy                        |
| Riku Laiho          | NCC Suomi Oy                   |
| Arto Nieminen       | NCC Suomi Oy                   |
</details>

## 1 Tausta
Tällä hetkellä rakennushankkeen tietomallit ovat yleinen osa hankkeen tarjouspyyntöjä ja niiden määrä- ja kustannuslaskentaa. Suunnittelijoiden tekemiä tietomalleja käyttävät ra-kennusliikkeet ja elementtitoimittajat mm. määrä- ja tarjouslaskennassa, hankkeen toteu-tuksen suunnittelussa ja aikatauluttamisessa jne. BEC2012-hankkeessa luodut vakioidut tietokentät, mallinnusohje ja mallinnustyökalut ovat alalla yleisesti käytössä.  BEC-ohjeistus ei kuitenkaan mahdollista koneluettavaa tiedonsiirtoa koska usea asia on BEC-ohjeistuksessa määritetty hankekohtaisesti sovittavaksi eikä tietokentille ole ohjeistettu sallittuja arvoja. Tiedot ovat saatavissa tietomalleista mutta edellyttää ihmisen taitoa lukea tietomallia ja samalla myös muita hankkeen suunnitelmadokumentteja. Esimerkkinä täl-laisesta käyttötapauksesta on esim. kuinka tunnistetaan tiililaattapintaiset SW-elementit hankkeen tietomallista ja muista elementeistä. Tällä hetkellä tunnistaminen ei onnistu au-tomaattisesti. Soveltamisohjeessa kuvattu ratkaisu elementtityyppien tunnistamiseen pohjautuu alalla yleisesti käytettyihin elementtityyppitunnuksiin, esim. V, R ja S jne.  Usein hankkeissa käytetään hankekohtaisesti sovittuna elementtityyppitunnuksessa myös pintakäsittelyä tai sijaintia tarkentavia numero- tai kirjainyhdistelyitä, kuten esim. V1-A. Nämä johtavat siihen, että elementtityyppejä ei voida tunnistaa koneluettavasti hankkeesta toiseen. 

IFC-tietomallistandardissa rakenneosien tunnistamiseksi objekteille voidaan määrittää IFC-luokkia, kuten esimerkiksi ifcwall. Useilla IFC-luokilla on lisäksi PredefinedType-ominaisuus, joka tarkentaa luokan tyyppiä. Esimerkiksi ifcwall-luokka voi sisältää Predefi-nedType-arvoja, kuten "standard" tai "movable". Standardissa määriteltyjen luokittelui-den tarkkuustaso riittää karkeaan luokitteluun, mutta ei mahdollista riittävän tarkkaa tunnistamista määrä- ja kustannuslaskentaa varten. Tämän vuoksi tarvitaan lisäattribuut-teja, jotta tietomallin avulla saavutetaan vaadittava tarkkuustaso. Ohjeessa kuvattu rat-kaisusta on tehty myös esimerkki malli Tekla Structures-ohjelmassa ja mallista IFC-tiedosto, eli ratkaisu on myös toteuttamiskelpoinen nykyisillä ohjelmistoilla.

Tämä soveltamisohje on tehty osana Rakennusteollisuus RT:n tuotetiedon ja toimitusket-jun digitalisoinnin kehityshanketta, BETK-työryhmän toimesta. Kehityshankkeen ensisijai-nen tavoite on edistää rakennusalan tuotteiden toimitusketjun hallinnan menetelmien siirtymistä manuaalisesta ja rakenteettomasta tiedonvaihdosta täysin rakenteelliseen ja koneluettavaan tiedonvaihtoon. Asiakirja on jatkuvasti päivittyvä ja sitä kehitetään edel-leen Rakennusteollisuus RT:n kehityshankkeen havaintojen perusteella. Tätä ohjetta täy-dentävät muut BETK-hankkeen julkaisut:

•	BETK Soveltamisohje_Tuoteyksilöinti ja -tunnistaminen[1]

•	Excel-taulukko muuttujista [2]

•	Soveltamisohje GS1 EPCIS (tapahtumatieto) käytöstä [syksyllä tehdään] [3]

•	Keskustelupaperi sijaintitiedoista rakennushankkeessa. [4]


## 2 2	Soveltamisohjeen tarkoitus ja rajaukset
Soveltamisohje keskittyy suunnittelijan tuottaman tietomallin sisällön vakiointiin tarjousvaiheessa. Samalla BEC2012-tietokenttien nimeämistä on tarkennettu ja IFC-malliin kirjoitettavia ominaisuuk-sia määritetty elementtityyppikohtaiseksi tiedonsiirron laadun parantamiseksi ja samalla on tieto-kenttien nimeämisessä pyritty huomioimaan mahdollisesti tulevaisuudessa kehitettävää muiden ra-kenneosien ja materiaalien tunnistamista ja vakiointia. Tiedonsiirron vakiointia on myös kehitetty li-säämällä sallittujen arvojen listauksia tietokenttiin joissa se mahdollista tehdä. Tietokentissä on huomioitu myös tietomallin rikastamista toteutusvaiheessa toimitusketjulta tulevilla tiedoilla.  So-veltamisohjetta täydentävät erillinen taulukko tietokentistä joissa mm. elementtien mittatiedot ja esimerkkitietomalli. Tätä soveltamisohjetta täydentää myös erillinen ohje elementtien yksilöinnistä toimitusketjussa  [1] ja esimerkki malli IFC-muodossa. Tätä soveltamisohjetta voidaan päivittää myöhemmin standardoinnin edetessä. Tämä soveltamisohje ei ota kantaa muuhun tarjouspyyntö aineistoon. 

## 3 Rakentamiskohteen tietomallin tietosisällöt tarjousvaiheessa
Tarjousvaiheessa tietomallissa käytettävät tietokentät elementtityyppien tunnistamiseen on kuvat-tu alla olevissa taulukoissa. Taulukoiden arvojen lisäksi hankintavaiheessa tarvittavat mitta- ja pin-ta-alojen tietokentät kuvattu erillisessä excel-taulukossa[2]. Excel-taulukossa on myös muita toteu-tusvaiheessa tarvittavia tietokenttiä sallittuine arvoineen

### 3.1 Elementin tuotetiedot tarjousvaiheessa

#### 3.1.1 Kokoonpanon tyyppi
Betonielementtien erottamiseen tietomallin muista objekteista voi käyttää Kokoonpanon-tyyppi kenttää. 

#### 3.1.2 Elementtityyppi
Elementtityyppi-tietokenttä tunnistaa mallin eri elementit. Tiedot syötetään tarjouksen yhteydessä ja päivitetään tarvittaessa toteutuksessa, jotta loppuselvityksessä voidaan tehdä tarvittaessa määrälaskenta.

#### 3.1.3 Raudoitus
Raudoitustietokentästä valitaan elementtityypin raudoitustyyppitieto. Description-kentässä tarkempi kuvaus. Esim R1 ja 2T10 ymp tai R2 ja 2T10 ymp , #10-200 mp. Tarvit-taessa hankkeessa käytetyt raudoituskoodit voi tarkentaa erillisessä mallin mukana toimi-tettavassa dokumentissa   . Esimerkkitaulukot raudoitustiedosta tarjous-vaiheessa ohjeen lopussa. 

#### 3.1.4 Pintakäsittely
Pintakäsittely-tietokenttään merkitään tarjousvaiheessa elementin ulkokuoren pintakäsit-tely. Jos samassa elementissä useampaa pintakäsittelyä käytetään tarvittaessa arvoja PK2, PK3 tarkentamaan tyypitystä. Toteutusvaiheessa käytetään BY40 mukaista koodausta, ks. kohta 4. 

#### 3.1.5 Vähähiilinen
Vähähiilinen-tiedon avulla mahdollista erotella tarjousvaiheessa vähähiiliseksi ajattelut tuotteet Kyllä/Ei-valinnalla.

#### 3.1.6 Tyyppielementti
Kyllä/-Ei-tieto elementistä, joka on varusteltu tietomallissa toteutusta vastaavaksi tyyp-pielementiksi.

#### 3.1.7	Työmaalla käännettävä elementti
Tieto työmaalla käännettävästä elementistä. Asennustyön hinnoittelua varten tarvittava tieto. Jos ei ole tietoa asennustavasta niin kenttä jätetään tyhjäksi.

## 4	Rakentamiskohteen informaatiomallin tuotetiedot
Tähän toimitusketjun tuottamat tiedot jotka halutaan tuoda tietomalliin toteutusvaihees-sa.   

## 5	Toimintaohjeita hankkeisiin  
**Numerointi**   
Tässä ohjeessa kuvattu elementtityyppien yksilöinti ja tunnistaminen ei vaikuta hankkeis-sa käytettyyn toteutusvaiheen elementtien numerointiin ja piirustusten nimeämiseen. Numerointi voidaan sopia hankekohtaisesti huomioiden mm. Tekla Strucrures-ohjelman numeroinnin ominaisuudet. Jos toteutusvaiheessa käytetään Tuoteyksilöinti ja -tunnistaminen ohjeessa [1] kuvattua tapaa elementtien yksilöintii ei ACN-numeron käytölle ole tarvetta.  

**Sijaintieto**  
Lohko- ja kerrostiedosta erillinen ohje  

**Revisiointi käytännöt**  

**Toimintaohje elementtien revisiointiin**  


###### Table 9. EPC Binary Encoding Schemes Use and Their Restrictions. The applicable method is determined by the required number of numeric or alphanumeric characters.

<html>
<table>
    <thead>
        <tr>             
           <th>EPC Scheme</th>
           <th>EPC-binary Coding Scheme</th>
           <th>EPC + Filter Bit Count</th>
           <th>Inclues Filter Value</th>
           <th>Serial number limitation</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan="2">sgtin</td>
            <td>sgtin-96</td>
            <td>96</td>
            <td>Yes</td>
            <td>Numeric-only, no leading zeros, decimal value must be less than 2³⁸ (i.e., decimal value less than or equal to 274,877,906,943)..</td>
        </tr>
        <tr>
            <td>sgtin-198</td>
            <td>198</td>
            <td>Yes</td>
            <td>All values permitted by GS1 General Specifications (up to 20 alphanumeric characters).</td>
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

###### Table 14. The QR code in the example contains the information shown in the table in GS1 Digital Link URI format: https://id.rt.fi/01/06400001000247/242/123456/21/12345678910

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
![RFID asemointi eng_3](https://github.com/user-attachments/assets/28703611-f01b-4721-930a-d60a53179d4a)



