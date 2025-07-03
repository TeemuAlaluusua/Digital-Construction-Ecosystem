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


## 2 Soveltamisohjeen tarkoitus ja rajaukset
Soveltamisohje keskittyy suunnittelijan tuottaman tietomallin sisällön vakiointiin tarjousvaiheessa. Samalla BEC2012-tietokenttien nimeämistä on tarkennettu ja IFC-malliin kirjoitettavia ominaisuuk-sia määritetty elementtityyppikohtaiseksi tiedonsiirron laadun parantamiseksi ja samalla on tieto-kenttien nimeämisessä pyritty huomioimaan mahdollisesti tulevaisuudessa kehitettävää muiden ra-kenneosien ja materiaalien tunnistamista ja vakiointia. Tiedonsiirron vakiointia on myös kehitetty li-säämällä sallittujen arvojen listauksia tietokenttiin joissa se mahdollista tehdä. Tietokentissä on huomioitu myös tietomallin rikastamista toteutusvaiheessa toimitusketjulta tulevilla tiedoilla.  So-veltamisohjetta täydentävät erillinen taulukko tietokentistä joissa mm. elementtien mittatiedot ja esimerkkitietomalli. Tätä soveltamisohjetta täydentää myös erillinen ohje elementtien yksilöinnistä toimitusketjussa  [1] ja esimerkki malli IFC-muodossa. Tätä soveltamisohjetta voidaan päivittää myöhemmin standardoinnin edetessä. Tämä soveltamisohje ei ota kantaa muuhun tarjouspyyntö aineistoon. 

## 3 Rakentamiskohteen tietomallin tietosisällöt tarjousvaiheessa
Tarjousvaiheessa tietomallissa käytettävät tietokentät elementtityyppien tunnistamiseen on kuvat-tu alla olevissa taulukoissa. Taulukoiden arvojen lisäksi hankintavaiheessa tarvittavat mitta- ja pin-ta-alojen tietokentät kuvattu erillisessä excel-taulukossa[2]. Excel-taulukossa on myös muita toteu-tusvaiheessa tarvittavia tietokenttiä sallittuine arvoineen

### 3.1 Elementin tuotetiedot tarjousvaiheessa

#### 3.1.1 Kokoonpanon tyyppi
Betonielementtien erottamiseen tietomallin muista objekteista voi käyttää Kokoonpanon-tyyppi kenttää. 


###### Table 10. Applicable Method: SGTIN-96. The SGTIN-96 encoding method is commonly used. However, the TDS 2.1 (EPC Tag Data Standard) also includes other encoding methods, such as SGTIN-198, which can be utilized if there is a need for longer serial numbers or serial numbers that include both letters and numbers.

<html>
<table>
    <thead>
        <tr>             
         <th colspan="3">IFC tietokentät</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>Tietosisältötarve</b></td>
            <td colspan="2"><b>Elementtityyppi</b></td>
        </tr>
          <tr>
            <td>Rajaukset</td>
            <td colspan="2">-</td>
        </tr>
        <tr>
            <td>Propertyset</td>
            <td colspan="2">BETK-hankinta</td>
        </tr>
         <tr>
            <td>Property Attribute</td>
            <td colspan="2">Sallitut arvot jaetaan kahteen ominaisuuskenttään:  
Elementin tyyppi, koodi ( AK jne)
Elementin tyyppi, kuvaus (Sokkelipalkki jne)
</td>
        </tr>
        <tr>
            <td rowspan="3">Sallitut arvot</td>
            <td><code>A</code></td>
            <td>Anturaelementti</td>
        </tr>
        <tr>
            <td>PH</td>
            <td>Pilariholkkielementti</td>
        </tr>
      <tr>
            <td>AN</td>
            <td>Sokkelielementti (ei-kantava)</td>
        </tr>
    </tbody>
</table>
</html>

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



