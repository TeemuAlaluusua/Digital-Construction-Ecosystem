# Tuoteyksilöinnin ja -tunnistamisen yhteentoimivuuden soveltamisohje

Here is a simple footnote[^1].
[^1]: My reference.

**Tilauksesta suunniteltavat rakennustuotteet**  
>Julkaisija: Rakennusteollisuus ry\
>Julkaistu: 9.1.2025  
Versio: 1.2  
Status: Julkaistu

## 1 Tausta
Rakennustuotteiden yksilöinti ja tunnistaminen on merkittävimpiä osatekijöitä kiinteistö- ja rakennusalan digitalisaatiossa. Vakioidut, yhteentoimivat ja globaalisti käytetyt tuoteyksilöinnin ja -tunnistamisen menetelmät mahdollistavat eri toimijoiden välisen tiedonvaihdon yhtenäisellä tavalla, riippumatta toimitusketjun osapuolesta.

GS1:n kehittämät toimitusketjun hallinnan standardit, kuten tuoteyksilöintiin hyödynnettävä tuotetunnus GTIN yhdessä EAN-viivakoodin kanssa, mahdollistavat eri toimijoiden välisen tiedonvaihdon yhtenäisellä tavalla. GTIN tuotetunnuksen avulla voidaan siis tunnistaa mikä tahansa kauppatavara, joka voidaan hinnoitella, tilata tai laskuttaa missä tahansa toimitusketjun vaiheessa, josta on tarpeen hakea ennalta määritettyjä tietoja.

Kaupan alalla tuotteet on yksilöity GTIN-koodien ja koneluettavien 1D EAN-viivakoodien kautta jo yli 50 vuotta, ja nyt tämä toimiva käytäntö on vakiintunut myös varasto-ohjautuvien (MTS) rakennustuotteiden osalta. Suomalaisessa rakennusteollisuudessa hyödynnetään kuitenkin tilauksesta suunniteltavia tuotteita, joiden osalta käytettävät yksilöinnin ja tunnistamisen menetelmät eivät ole vakiintuneet. Rakennustuotteiden yksilöinti on tiedonvaihdon näkökulmasta tärkeää, sillä rakennustuotteiden käyttöikä on yleensä pitkä, ja jotkut niistä ovat aktiivisessa käytössä jopa yli 100 vuotta. Uusien materiaalien nopea kehitys sekä kestävyyden ja kiertotalouden kasvava merkitys ovat lisänneet tarvetta hallita rakennetuissa kohteissa käytettyjä rakennustuotteita ja niiden ominaisuuksia elinkaaren ajan.

## 2 Soveltamisohjeen tarkoitus
Tämä soveltamisohje on tehty osana Rakennusteollisuus RT:n tuotetiedon ja toimitusketjun digitalisoinnin kehityshanketta, BETK-työryhmän toimesta. Kehityshankkeen ensisijainen tavoite on edistää rakennusalan tuotteiden toimitusketjun hallinnan menetelmien siirtymistä manuaalisesta ja rakenteettomasta tiedonvaihdosta täysin rakenteelliseen ja koneluettavaan tiedonvaihtoon. Asiakirja on jatkuvasti päivittyvä ja sitä kehitetään edelleen Rakennusteollisuus RT:n kehityshankkeen havaintojen perusteella.

Soveltamisohje keskittyy toimitusketjun digitalisoinnissa tarvittavaan tuotteiden yksilöintiin ja koneelliseen tunnistamiseen. Soveltamisohjeessa kuvataan malli avointen GS1-standardien soveltamisesta tilauksesta suunniteltavien (ETO) rakennustuotteiden toimitusketjun hallintaan, käyttäen esimerkkinä betonielementtejä. GS1:llä on tilauksesta suunniteltavien ja valmistettavien tuotteiden yksilöintiin liittyen käynnissä kansainvälistä standardointityötä. Tämä soveltamisohje on tehty standardoinnin ollessa kesken, joten sitä tullaan tarvittaessa päivittämään myöhemmin.

## 3 Rakennustuotteiden SGTIN-tuoteyksilöinti
Tuoteyksilöinti on edellytys toimitusketjun digitalisoinnille tuotteiden valmistuslogiikasta riippumatta. Betonielementtien osalta tuoteyksilöinti on skaalautumisen mahdollistamiseksi päätetty toteuttaa tuoteryhmästä riippumattomaan, avoimeen ja kansainväliseen standardiin pohjautuen. GS1-standardin mukainen GTIN-koodi on laajasti käytetty ratkaisu tuotteiden yksilöintiin eri toimialoilla ja sen soveltaminen valikoitui hankkeessa lähtökohdaksi myös tilauksesta suunniteltavien tuotteiden (betonielementtien) yksilöinnille.

Perinteisesti GTIN-koodeilla on yksilöity ns. varasto-ohjautuvia-tuotteita (MTS), jolloin kaikille identtisille tuotteille on määritetty sama GTIN. Yhdistämällä GTIN-koodiin sarjanumero, luodaan yksilöllinen tunniste, jonka avulla keskenään identtiset tuotteet voidaan erottaa toisistaan. Tätä yhdistelmää kutsutaan SGTIN-koodiksi.

Betonielementit ovat luonteeltaan tilauksesta valmistettavia (MTO) ja tilauksesta suunniteltavia (ETO) tuotteita,jolloin niiden yksilöiminen GTIN-koodeilla poikkeaa lähtökohtaisesti varasto-ohjautuvista tuotteista. On mahdollista luoda jokaiselle yksilölliselle betonielementille oma GTIN-koodinsa, mutta BETK-työryhmän osalta on päädytty hyödyntämään GS1-standardia ns. kolmella yksilöinnin tasolla (esitetty taulukossa 1). Tässä mallissa GTINkoodilla yksilöidään tietyn valmistajan tietyntyyppinen perustuote. Made-to-Order varianttinumeron avulla yksilöidään tämän perustuotteen tietty variantti ja lopulta sarjanumerolla yksilöidään perustuotteen saman variantin identtiset yksilöt. Tässä tapauksessa pelkkä GTIN ei siis yksilöi tiettyä tuotetta, vaan yleisen luokan mahdollisista tilauksen perusteella valmistettavista tuotteen variaatioista.

###### Taulukko 1. Tuoteyksilöinnin hierarkia tasot tarkempaan yksilöintiin
| Tuoteyksilöinnin tasot             | Tunniste                                             |
|:-----------------------------------|:-----------------------------------------------------|
| **Taso 1** Tuoteryhmä / Perustuote | GTIN                                                 |
| **Taso 2** Tuotevariaatio          | GTIN + MTO Varianttinumero                           |
| **Taso 3** Tuoteyksilö             | GTIN + (MTO Varianttinumero) + Sarjanumero (SGTIN)   |


### 3.1 GS1-sovellustunnusten käyttäminen ETO-tuotteiden yksilöintiin

GS1-sovellustunnukset (AI = Application Identifiers) ovat numeerisia etuliitteitä, joita käytetään viivakoodeissa ja EPC/RFID-tunnisteissa määrittämään tietoelementtien merkitys ja muoto. GS1-sovellustunnusten käyttö mahdollistaa eri tietoelementtien erottamisen toisistaan viivakoodeissa tai EPC/RFID-tunnisteessa. GS1-standardi kattaa yli 100 sovellustunnusta. Jokainen sovellustunniste on oletusarvoisesti kaksi-, kolmi- tai nelinumeroinen luku. Listaus kaikista GS1-sovellustunnuksista on saatavilla GS1:n verkkosivuilla osoitteessa: https://ref.gs1.org/ai/.

Betonielementin yksilöinnissä minimitietovaatimuksissa tarvittaviksi GS1-sovellustunnuksiksi on tunnistettu seuraavat: (01) GTIN, (242) Made-to-Order variation number ja (21) Serial number. 

GS1-standardissa ei ole kansalliselle Elementtitunnukselle, GUID:lle ja verkkotunnukselle omaa GS1-sovellustunnusta, joten niiden sisällyttämisessä tiedonkantajaan on BETK-projektissa päätetty käytettävän sovellustunnuksia (91) Company interal information, (92) Company internal information ja (99) Company internal information. Numerolla 9 alkavia GS1-sovellustunnuksia käytetään vain silloin, mikäli kyseiselle tiedolle ei ole (vielä) määritetty omaa GS1-sovellustunnustaan. 

Huom! Verkkotunnuksen käsittely RFID-tunnisteissa on tämän ohjeen julkaisuhetkellä käsiteltävänä GS1:n kansainvälisessä standardinkehityksessä. Tuleva standardi ei välttämättä vastaa tässä esitettyä ratkaisua, mutta ohjeistus tullaan päivittämään standardin valmistuessa sen mukaiseksi. Optisessa tunnistamisessa (esim. QR-koodi) tämän tiedon sisällyttämisessä käytetään GS1 Digital Link URI syntax 1.5.0 -standardin mukaista menettelyä.

###### Taulukko 2. Tiedonkantajaan lisättävät tilauksesta suunniteltavien (ETO) rakennustuotteen minimitietovaatimukset.
| AI | Tieto | Esimerkki |
|----|-------|-----------|
| (01) | GTIN-koodi | 06400001000247 |
| (242) | MTO varianttinumero | 123456 |
| (21) | Sarjanumero | 12345678910 |

###### Taulukko 3.Tiedonkantajaan lisättävät valinnaiset lisätiedot. *Huom! Optisessa tunnistamisessa (esim. QR-koodi) verkkotunnuksen sisällyttämisessä käytetään GS1 Digital Link URI syntax 1.5.0 -standardin mukaista menettelyä

| AI | Tieto | Esimerkki |
|----|-------|-----------|
| (91) | Elementtitunnus | V1001 |
| (92) | GUID | ba34cf17-0c4b-4c6f-9295-cae05aa74ad4 |
| (99) | Verkkotunnus | id.rt.fi |

### 3.2 GS1- yritystunniste
GS1-yritystunnus, eli GS1 Company Prefix, on yksilöllinen numerosarja, jonka GS1-organisaatio myöntää yrityksille maailmanlaajuisesti. Yritystunniste on asiakaskohtainen, eikä samaa tunnistetta tai sen pohjalta tehtyjä numerosarjoja voi olla minkään muun toimijan käytössä. GS1-yritystunnusta käytetään monissa standardoiduissa tunnistusmenetelmissä, kuten viivakoodeissa ja RFID-tunnisteissa, ja se on pohjana GTIN-, GLN- ja SSCC-koodien muodostamisessa.

Suomessa GS1-yritystunnisteita myöntää GS1 Finland ja sellaisen voi tilata GS1 Finlandin verkkokaupasta. Oikean GS1-yritystunnisteen valinnassa tulee huomioida tarvittavien GTIN-koodien määrä, johon on tarvittaessa saatavilla apua GS1 Finlandin asiakaspalvelusta.

### 3.3 GTIN-koodin muodostaminen
GTIN-koodien muodostaminen edellyttää, että yrityksellä on käytettävissään GS1-yritystunniste (GS1 Company Prefix, GCP). GTIN-koodien muodostaminen taas mahdollistaa tuotteiden yksilöllisen tunnistamisen perustuotteen tasolla.

GTIN-koodi alkaa GS1-yritystunnisteella, jonka pituus GS1 Finlandilta saatavilla olevilla vaihtoehdoilla voi olla 7–11 numeroa. Tämän jälkeen seuraavat 1–6 numeroa voi määrittää itse, ja näissä suositellaan käytettäväksi juoksevaa numerointia. Käytettävissä olevien numeroiden määrä riippuu yritystunnisteen pituudesta. Koodin viimeinen, eli 13. numero, on tarkistusnumero, joka lasketaan 12 ensimmäisen numeron perusteella Modulo 10 -algoritmilla. Tarkistusnumeron laskemiseen voi käyttää esimerkiksi GS1 Finlandin tarjoamaa tarkistusnumerolaskuria: https://gs1.fi/fi/tarkistusnumerolaskuri

###### Taulukko 4. GTIN-koodin rakenne

| GS1-sovellustunnus | GS1-yritystunniste ---> <--- tuotekohtainen numero |  Tarkistusnumero |
|----|-------|-----------|
| (01) |  0 N1 N2 N3 N4 N5 N6 N7 N8 N9 N10 N11 N12 | N13|
 
Viivakoodeissa ja RFID-tunnisteissa GTIN-koodin ilmaisemiseen käytettävä sovellustunnus on (01). GS1:n kansainvälisessä standardikehityksessä käsitellään parhaillaan tilauksesta valmistettavien ja tilauksesta suunniteltavien tuotteiden yksilöintiä. Tämän standardinkehitystyön tuloksena voi tulla muutoksia tilauksesta valmistettavien/suunniteltavien tuotteiden GTIN-koodien ilmaisemiseen. Tämä ohje päivitetään standardin valmistuessa.

Huom! GTIN-koodin pisin versio on 14-merkkiä pitkä ja tätä lyhyemmät GTIN-koodit täydennetään koodin eteen lisättävillä nollilla 14-merkkiä pitkiksi. GTIN-koodi ei voi olla tätä pidempi.

GS1 Finland tarjoaa yritystunnisteasiakkailleen käyttöön GS1 Rekisteri -palvelun GTIN-koodien muodostamiseen. Muodostamalla GTIN-koodin GS1 Rekisteri -palvelussa, voi varmistua niiden oikeasta muodosta.

### 3.4 Variaatioiden yksilöinti
Betonielementtien variaatioiden yksilöinnissä GTIN-koodiin yhdistetään lisätunnisteena variaationumero (Madeto-Order variation number). Variaationumero mahdollistaa sen, että voidaan tietää joidenkin elementtien olevan keskenään samanlaisia. Toisin sanoen, kun monta elementtiä, joilla on samat tekniset tiedot, valmistetaan kerralla, niillä kaikilla on sama GTIN-koodin ja variaationumeron yhdistelmä.

Viivakoodeissa ja RFID-tunnisteissa käytetään sovellustunnusta (242) ilmaisemaan variaationumero. GS1-standardin mukaan variaationumero on numeerinen ja vaihtuvapituinen, enintään kuusi numeroa pitkä.

###### Taulukko 5. MTO-Varianttinumero-koodin rakenne

| GS1-sovellustunnus | Made-to-Order variation number |
|--------------------|--------------------------------|
| (242)              | N1 ----vaihtuva pituus --->N6  |

### 3.5 Sarjanumerointi
Yhdistämällä GTIN-koodiin (tai GTIN-koodin ja variaationumeron yhdistelmään) sarjanumerointi, voidaan yksilöidä ja erottaa toisistaan keskenään identtiset elementit. GS1-sovellustunnus (21) osoittaa, että tietokenttä sisältää sarjanumeron. GS1-standardin mukaan sarjanumero on aakkosnumeerinen ja enintään 20 merkkiä pitkä.
Huom! Valittu RFID-tunniste voi asettaa rajoituksia sarjanumeron pituudelle ja aakkosten käytölle, joten asia on hyvä tarkistaa RFID-ratkaisutoimittajalta.
###### Taulukko 6. Sarjanumero-koodin rakenne

| GS1-sovellustunnus | Serial number                  |
|--------------------|--------------------------------|
| (21)               | X1 ----vaihtuva pituus --->X20 |

### 3.6 Elementtitunnus
Elementille määritetty tunnus, joka on ihmisen helposti luettavissa, ja voi sisältää tietoa esimerkiksi elementin
tyypistä tai asennuskerroksesta. Elementtitunnuksen ei tarvitse olla globaalisti yksilöllinen.
###### Taulukko 7. Elementtitunnukset rakenne

| GS1-sovellustunnus | Elementtitunnus                |
|--------------------|--------------------------------|
| (91)               | X1 ----vaihtuva pituus --->X20 |

### 3.7 GUID
GUID, toiselta nimeltään UUID, on globaalisti yksilöllinen tunnuste, joka voidaan määrittää mallinnusohjelman toimesta tai muulla yksilöllisyyden varmistavalla tavalla.

###### Taulukko 8. GUID-koodin rakenne

| GS1-sovellustunnus | GUID                                 |
|--------------------|--------------------------------------|
| (92)               | xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx |


### 3.8 Verkkotunnus
Yhdistämällä verkkotunnus ja muita yksilöintitietoja voidaan hakea internetin välityksellä lisätietoja yksilöidystä
tuotteesta URL-osoitteen avulla, mikäli tietojen toimittaja on toteuttanut ominaisuuden ja pitää sitä edelleen
toiminnassa.
###### Taulukko 9. Verkkotunnuksen rakenne. * Huom! Optisessa tunnistamisessa (esim. QR-koodi) tämän tiedon sisällyttämisessä käytetään  
edellä esitetyn GS1 Digital Link URI syntax 1.5.0 -standardin mukaista menettelyä.
GS1-sovellustunnus Verkkotunnus
(99) <alitunnus.><tunnus.ylätunnus>, jossa <alitunnus.> toistuu 0…n kertaa)
Tässä dokumentissa määritellään kaksi tapaa yhdistää verkkotunnus muihin yksilöintitietoihin URL-osoitteen
muodostamiseksi. Tuloksena muodostuu GS1 Digital Link -standardin tai IEC 61406 -standardin mukainen URLosoite.  

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
Lisäksi voidaan määrittää GUID-tunnisteeseen perustuva IEC 61406 Identification Link standardin mukainen URLosoite seuraavasti:  
```https://<verkkotunnus>/<GUID>```
Jolloin esimerkiksi muodostuu: https://id.rt.fi/ba34cf17-0c4b-4c6f-9295-cae05aa74ad4

## 4 Automaattinen tunnistaminen ja tiedonkantajat
Tuoteyksilöinnin lisäksi on valittava käytettävä tunnistusteknologia ja tiedonkantaja, jotka mahdollistavat niiden koneellisen luennan. Tunnistusteknologian valinnassa tulee huomioida käyttötarkoituksen ja olosuhteiden asettamat vaatimukset. Automaattiseen tunnistamiseen ja tiedonkeruuseen tarkoitettuihin GS1-tietokantajiin voidaan tallentaa erilaisia tietomääriä eri liiketoimintaprosesseja ja kaupankäynnin vaatimuksia varten. GS1-tietokantajiin koodatut tiedot eivät ainoastaan yksilöi tuotteita yksiselitteisesti kaikilla Tuoteyksilöinnin hierarkia tasoilla, vaan ne tarjoavat myös pääsyn tuotetietoihin ja näkyvyyden tuotteiden liikkeisiin toimitusketjussa.  

Betonielementtien tuotetunnistamisen minimitietovaatimusten välittämisessä soveltamisohje suosittelee vähintään optiseen tunnistamiseen perustuvan 2D-koodin lisäämistä elementin tuote-etikettiin valmistuksen yhteydessä. GS1-standardissa vaihtoehdot tähän ovat GS1 DataMatrix -koodi sekä QR-koodi GS1 Digital Link -standardin mukaisella tietosisällöllä. Elementin tuote-etiketissä käytettävän 2D-koodin rinnalla, voidaan käyttää myös RFID-teknologiaan perustuvaa koneluettavaa tiedonkantajaa, joko elementin tuote-etiketissä tai betonielementtiin valettuna. Kuvassa 1 on esitetty tiedonkantajien käyttöä ja merkintää betonielementtien osalta.

Tässä soveltamisohjeessa on kuvattu tuotetunnistusta GS1 DataMatrix -koodin avulla, joka soveltuu BETK-työryhmässä määritettyyn käyttötarkoitukseen. Vaihtoehtona on esitelty lyhyesti myös GS1 Digital Link -standardin mukainen QR-koodi ja sen hyödyntämisen mahdollisuuksista on tarvittaessa saatavissa lisätietoa GS1 Finlandilta.  

###### Kuva 1. Koneellinen tuotetunnistaminen GS1-tiedonkatajien avulla
Betonielementtien automaattisessa tunnistamisessa tehokkaimmaksi tiedonkantajaksi on havaittu EPC/RFID
Gen-2 UHF -standardiin perustuva passiivinen etäluettava tunniste, josta elementin tunnistenumero voidaan lukea tehokkaasti myös useampien metrien päästä ilman suoraa näköyhteyttä itse tunnisteeseen.

### 4.1 Tuotetunnistus passiivisella EPC/RFID Gen2 UHF -tunnisteella
Tämä ohje perustuu EPC / RFID Gen2 Radio -protokollaan, joka määrittelee fyysisen tiedonsiirron RFID-sirun ja RFID-lukijan välillä käskyillä RFID-lukijan ohjaamiseksi suhteessa RFID-tunnisteisiin. EPC / RFID Gen2 on ISO-standardi ja kattaa erilaisia toiminnallisuuksia, kuten suojauksen ja laajennetun käyttäjämuistin.

GS1 on julkaissut TDS:n (Tag Data Standard), joka määrittelee miten GS1-standardin mukaiset yksilöintiavaimet, kuten SGTIN sisällytetään etäluettaviin EPC Gen2 RFID -tunnisteisiin. TDS-standardi on avoimesti kaikkien käytettävissä ja se onkin jo nykyisin laajasti käytössä RFID-tunnistamisessa eri toimialoilla.

Tuotetunnistuksessa vaadittavat tiedot sisällytetään EPC Gen2 RFID -tunnisteisiin TDS-standardin mukaisesti, tarvittavia GS1-sovellustunnuksia hyödyntäen. Tietojen koodaamiseen käytetään tunnisteen EPC-muistia (EPC memory) ja tarvittavilta osin käyttäjämuistia (User memory).

EPC-muisti on suunniteltu sisältämään EPC-koodi, eli tunnistettavan asian yksilöivä GS1-standardin mukainen tunnistenumero. Betonielementtien yksilöinnissä EPC-muistiin koodataan elementin SGTIN-koodi. Tämä mahdollistaa elementin yksilöivän tunnistenumeron nopean lukemisen.

Käyttäjämuistia käytetään, kun RFID-tunnisteelle on tarve saada enemmän tietoa kuin EPC-muistiin mahtuu.  
BETK-projektissa on tunnistettu, että tunnisteeseen on tarve sijoittaa lisätietoa kuten variaationumero (Madeto-Order Variation Number), elementtien luokittelussa käytettävä elementtitunnus ja suunnitteluohjelmiston luoma GUID-tunniste. GTIN:n ja SGTIN:n rakenne viivakoodeissa ja EPC/RFID Gen 2V2 RFID-tunnisteissa

###### Taulukko 10.Käytössä olevat EPC-binäärikoodausjärjestelmät ja niiden rajoitukset. Sovellettava menetelmä määräytyy numeeristen tai alfanumeeristen merkkien määrätarpeen mukaan.


###### Taulukko 11. Sovellettava menetelmä SGTIN-96. Standardissa TDS 2.1. (EPC Tag Data Standard) löytyy myös muita sovellusmenetelmiä mm. SGTIN-198, joita voidaan käyttää, mikäli on tarve esimerkiksi pidemmälle (tai numeroiden lisäksi myös kirjaimia sisältävälle) sarjanumerolle.

SGTIN-96 tietosisältö  
EPC SGTIN-96 Arvo Kommentti  
Otsikko (Header) 48 Numero SGTIN-96:lle  
Filter-arvo (Filter value) 0 0 = Soveltuva arvo tuotteelle, jota ei lueta kassapisteellä  
Partition-arvo 1,2,3,4,5 tai 6 1 = 11-numeroinen GS1-yritystunniste ja 2 numeroa tuotenimikkeelle + laajennustunnukselle  
2 = 10-numeroinen GS1-yritystunniste ja 3 numeroa tuotenimikkeelle + laajennustunnukselle  
3 = 9-numeroinen GS1-yritystunniste ja 4 numeroa tuotenimikkeelle + laajennustunnukselle  
4 = 8-numeroinen GS1-yritystunniste ja 5 numeroa tuotenimikkeelle + laajennustunnukselle  
5 = 7-numeroinen GS1-yritystunniste ja 6 numeroa tuotenimikkeelle + laajennustunnukselle  
6 = 6-numeroinen GS1-yritystunniste ja 7 numeroa tuotenimikkeelle + laajennustunnukselle  
GS1-yritystunniste (GS1 GCP) N…11 GS1-yritystunniste: 6,7,8,9,10 tai 11 numeroa
Tuotenimikkeen numero N…7 Riippuen GS1-yritystunnisteen pituudesta 1–7 numeroa
Sarjanumero N…12 Enintään 12 numeroa (suurin sallittu arvo = 274 877 906
943) Sarjanumeron ei tarvitse olla tasan 12 numeroa.
Etunolla ei ole sallittu.

**Esimerkki tietosisällöstä EPC / Gen2 RFID -tunnisteessa:**
RFID Tag EPC Memory Bank Contents (hexadecimal): 301586A004000602DFDC1C3E
EPC Tag URI: urn:epc:tag:sgtin-96:0.6400001.000024.12345678910

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
**• Jakoparametri**   
Määrittää, mihin kohtaan erotinmerkki ( . ) asetetaan GS1-yritystunnuksen ja tuotetunnuksen välille. Jakoparametri riippuu GS1-yritystunnuksen pituudesta. Viimeinen erotinmerkki ( . ) URI:ssä erottaa GTINnumeron (Global Trade Item Number) sarjanumerosta.  
**• Tarkistusnumero**  
Käytetään virheentarkistukseen GTIN-tunnuksissa. Tarkistusnumeroa ei kuitenkaan sisällytetä EPC-koodiin RFID-tunnisteessa, sillä RFID-prosessoinnissa sitä ei tarvita.  
**Käyttäjämuisti-osio**  
Muu lisätieto sijoitetaan RFID-sirun käyttäjämuisti-osioon (User memory) seuraavalla tavalla:
AI Arvo
(91) Internal → Elementtitunnus V1001
(92) Internal → GUID ba34cf17-0c4b-4c6f-9295-cae05aa74ad4
(99) Internal → Verkkotunnus id.rt.fi  
**RFID-tunnisteiden toteuttaminen**  
RFID-tunnisteiden ohjelmointia varten on hyvä olla yhteydessä tunnistamisen ratkaisuihin erikoistuneeseen yritykseen tai yrityksiin. Tunnistamisen ratkaisuja tarjoavia yrityksiä on koottu mm. GS1:n kumppanisivulle ja RFID Lab Finlandin ry:n sivulle.  

#### 4.1.1 RFID-tunniste symbolin käyttö  
RFID-teknologiaa käytettäessä tuotteiden automaattiseen tunnistamiseen on syytä varmistaa, että RFID-tunniste symboli sisällytetään tuote-etiketteihin sekä tuotantosuunnitelmiin. Symbolin tulee olla standardin mukainen, helposti tunnistettavissa ja sijoitettu niin, että se osoittaa selkeästi RFID-tunnisteiden sijainnin ja käytön.  

RFID-tunniste symboli
RFID-tunnistesymbolina suositellaan käytettäväksi ISO 7000-3010 -standardin mukaista, vapaasti saatavilla olevaa yleistä RFID-symbolia. Symbolin käytön tulee täyttää ISO/IEC 29160:2020-standardin vaatimukset, erityisesti silloin kun symbolia
hyödynnetään osoittamaan RFID-tunnisteiden sijaintia. [1] [2]

Koko
RFID-tunniste symbolin (ISO 7000-3010) tulisi olla vähintään (5 × 5) mm:n kokoinen, ja tämän ympärille tulisi jättää 1 mm:n vapaa alue. Kun RFID-tunniste symboli
esitetään matalakontrastisena, sen on oltava riittävän suuri, jotta se on helposti tunnistettavissa tavanomaisissa käyttöolosuhteissa. [2]

###### Kuva 2. Yleinen RFID-symboli (ISO 7000-3010). [3]

**Soveltaminen betonielementtien käyttöympäristössä**
RFID-merkintä symboli on sijoitettava siten, että se näkyy helposti niille, jotka yrittävät etsiä tai lukea varsinaista RFID-tunnistetta. RFID-tunnistesymbolin käyttöä suositellaan betonielementtien tuotantosuunnitelmissa osoittamaan RFID-tunnisteiden sijaintia (esimerkki kuvattu liitteessä 1). RFID-tunnisteen käyttö tulee merkitä RFID-tunniste symbolin avulla, ja käytettävä tunnistetyyppi sekä sijaintitiedot lisätään osaksi betonielementin tuoteosaluetteloa.

**RFID-tunnisteen sijoittaminen fyysiseen tuotteeseen**
RFID-merkittyjen objektien luettavuuteen vaikuttavat useat tekijät, kuten RFID-siru, RFID-antenni ja kotelointi (koko RFID-tunniste). Lisäksi ympäristö, jossa RFID-tunniste luetaan, vaikuttaa olennaisesti luettavuuteen. Ympäristö, jossa on paljon metalliesineitä, voi esimerkiksi aiheuttaa ei-toivottuja heijastuksia radioaaltoihin, jolloin luenta vaikeutuu tai luetaan väärä kohde.

Markkinoilla on erilaisia RFID-tunnisteita, jotka soveltuvat eri käyttötarkoituksiin. RFID-tunnisteita voidaan käyttää betonielementtien toimintaympäristössä betonielementtien sisään valettuna, elementtien pinnalla, tai osana betonielementteihin kiinnitettävää tuote-etikettiä. Betonielementtiin valettaessa, RFID-tunnisteen luettavuuteen vaikuttaa sen ympärillä oleva materiaali, joten valittavan RFID-tunnisteiden tulee olla sellainen, että se on luettavissa sitä ympäröivän betonin läpi riittävästä syvyydestä. Ulkoisessa aplikaattorilla muodostetussa tuoteetiketissä tulee olla merkintä RFID-tunnisteen käytöstä sekä tarkennus siitä, sijaitseeko tunniste itse lapussa vai valettuna elementin sisällä. RFID:n käytön hyödyt perustuvat automatisoituihin lukutapahtumiin ja niistä syntyvään tapahtumatietoon. Lukutapahtumalla tarkoitetaan yksinkertaistettuna sitä, että lukijalaite havaitsee tietyn RFID-tunnisteen.

### 4.2 Tuotetunnistus GS1 DataMatrix 2D-koodilla
GS1 DataMatrix on GS1:n kehittämä kaksiulotteinen viivakoodi, joka voidaan tulostaa yksittäisistä pisteistä tai neliöistä koostuvana neliön tai suorakaiteen muotoisena symbolina. GS1 DataMatrix voi sisältää perinteistä lineaarista viivakoodia suuremman määrän tietoa. Siihen on mahdollista koodata jopa 3116 numeerista merkkiä tai 2335 alfanumeerista merkkiä. GS1 sovellustunnusten avulla GS1 DataMatrixiin voidaan sisällyttää useita erityyppisiä tietoja, kuten esimerkiksi määritetyt betonielementtien minimitietovaatimukset. GS1 DataMatrixin lukeminen vaatii kamerapohjaisen skannerin.

Esimerkin tietosisältö
GS1-sovellustunnus (AI) Arvo
AI 01 = GTIN 06400001000247
AI 242 = MTO variation number 123456
AI 21 = Serial number 12345678910
AI 91 = Internal (elementtitunnus) V1001
AI 92 = Internal (GUID) ba34cf17-0c4b-4c6f-9295-cae05aa74ad4
Kuva 3. Esimerkki betonielementtien minimitietovaatimukset sisältävästä GS1 DataMatrix -koodista
GS1 DataMatrix -tunnisteen koko ja laatu
Viivakoodin fyysinen koko vaihtelee sen sisältämän tiedon määrän mukaan. Viivakoodin resoluution (X-dimensio) on oltava vähintään 0,38 mm ja enintään 0,45 mm. Merkinnöissä käytettävien GS1 2D-viivakoodien laadun
tulee täyttää ISO / IEC 15415 -standardin vaatimukset. Näin voidaan varmistua niiden luettavuudesta.
Merkintöjen tulostamista varten on hyvä olla yhteydessä tunnistamisen ratkaisuihin erikoistuneeseen yritykseen
tai yrityksiin. Tunnistamisen ratkaisuja tarjoavia yrityksiä on koottu mm. GS1:n kumppanisivulle.

## 4.3 Tuotetunnistus GS1 Digital Link -standardin mukaisella QR-koodilla
Mikäli tunnisteen avulla halutaan yksilöinnin ja tunnistamisen lisäksi viestiä kuluttajalle/käyttäjälle älypuhelimen tai muun vastaavan laitteen kautta, voidaan tunnisteena käyttää GS1 Digital Link -standardin mukaista QR-koodia. Tavallisesta QR-koodista tämä eroaa siten, että sen tietosisältö on GS1-standardin määrittämä. Standardi varmistaa, että koodit ja niiden sisältämät tiedot ovat rakenteeltaan yhdenmukaisia ja siten liikuteltavia eri järjestelmien ja toimijoiden välillä sekä luettavissa ja tulkittavissa viivakoodinlukijoilla.

GS1 Digital Link URI:n sisältävä QR-koodi palvelee kahta käyttötarkoitusta:

**1. Tuotteen yksilöinti ja tunnistaminen offline-tilassa**  
Sitä voidaan käyttää ilman verkkoyhteyttä tuotteen yksilöimiseen ja tunnistamiseen viivakoodinlukijoilla, aivan kuten perinteisiä EAN-viivakoodeja. Tuotteen yksilöinnissä käytetään QR-koodiin sisällytettävää GS1-standardin mukaista GTIN-koodia ja tarvittavia lisätietoja, kuten MTO varianttinumeroa ja sarjanumeroa.

**2. Verkossa jaettava tietosisältö**  
Sitä voidaan käyttää kuten mitä tahansa QR-koodia, eli ohjaamaan älypuhelimen tai muun vastaavan laitteen käyttäjä verkossa olevaan sisältöön. Erilaiset sovellukset voivat suorittaa saman QR-koodin lukemisen kautta myös muita toimintoja ja näyttää erilaista sisältöä.

GS1 Digital Link URI:ssa käytetään GS1-sovellustunnuksia tietojen sisällyttämiseen. Alla olevassa esimerkissä on muodostettu taulukossa esitetyt minimitietovaatimukset sisältävä GS1 Digital Link URI.

<html>
 <td><img src=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190710102234/download3.png" 
                alt="GFG Logo" width="500" 
                height="500">
            </td>
        </tr>
<table>
    <thead>
        <tr>            
            <th colspan="2">Esimerkin tietosisältö</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>GS1-sovellustunnus (AI)</b></td>
            <td><b>Arvo</b></td>
        </tr>
        <tr>
            <td>AI 01 = GTIN</td>
            <td>06400001000247</td>
        </tr>
         <tr>
            <td>AI 242 = MTO variation number</td>
          <td> 123456</td>
        </tr>
        <tr>
            <td>AI 21 = Serial number</td>
            <td>12345678910</td>
        </tr>
    </tbody>
</table>
</html>

##### Kuva 4. Esimerkin QR-koodi sisältää taulukossa esitetyt tiedot GS1 Digital Link URI -muodossa:
https://id.rt.fi/01/06400001000247/242/123456/21/12345678910

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
EPC  | Sähköinen tuotekoodi (engl. Electronic Product Code). Kts EPC Tag Data Standard ISO/IEC 15962
EPC-muisti  | RFID-tunnisteen muisti, johon sähköinen tuotekoodi kirjoitetaan, eli tunnisteen perusmuisti
ETO  | ETO (Engineer-To-Order) tarkoittaa tilauksesta suunniteltavien tuotteiden valmistuslogiikkaa.
GS1 DataMatrix  | GS1-standardin mukainen 2D-koodi, johon voidaan sisällyttää enemmän tietoa kuin perinteiseen EAN-viivakoodiin. ISO/IEC 16022
GS1 AI  | GS1-sovellustunnukset (Application Identifier, AI) ovat 2–4 numeron pituisia tunnuksia, joita käytetään GS1-128-, GS1 DataMatrix- ja GS1 DataBar -viivakoodeissa sekä EPC/RFID-tunnisteissa.
GTIN  | (Global Trade Item Number) on GS1:n tuotetunniste standardi (ISO/IEC 15459-6 & ISO/IEC 6523).
GUID  | GUID (Globally Unique IDentifier) on mallinnusohjelman antama tai muulla tavalla luotu kullekin osalle yksilöllinen tunniste. Kulkee myös nimellä UUID (Universally Unique IDentifier). (määritelty ISO/IEC 11578:1996 Information technology - Open Systems Interconnection - Remote Procedure Call (RPC) -määrittelyssä ja sekä ITU-T Rec. X.667 | ISO/IEC 9834-8:2005)
MTO | MTO (Make-To-Order / Made-To-Order) tarkoittaa tilausohjautuvaa tuotantoa, jossa tuotteet valmistetaan asiakastilausten mukaisesti valmiiden tuotesuunnitelmien pohjalta.
MTS | MTS (Make-To-Stock) termillä tarkoitetaan varasto-ohjautuvien tuotteiden valmistuslogiikkaa.
RFID  | RFID (Radio Frequency Identification) termillä tarkoitetaan radiotaajuisia etätunnisteita (sisältää antennin ja mikropiirin).
SGTIN  | GTIN-koodin ja sarjanumeron yhdistelmä, jolla voidaan erottaa identtiset tuoteyksilöt toisistaan.
Tag  | RFID-tunniste, joka sisältää sirun ja antennin. Käytetään objektien yksilölliseen tunnistamiseen.
User memory  | RFID käyttäjämuisti tai lisämuisti
UHF tunniste | Korkeataajuinen (850–960 MHZ) RFID tunniste
URI  | URI (Uniform Resource Identifier) on tietoverkossa sijaitsevan tiedon tunniste. URL on aina myös URI, mutta URI ei välttämättä ole URL. Esimerkiksi https://rt.fi tai urn:ISBN:952-9842-34-1
URL  | URL (Uniform Resource Locator) sisältää tiedon hakemiseen tarvittavan tiedon, kuten protokollan (esim. https) ja palvelimen. Esimerkiksi https://rt.fi
Verkkotunnus | Verkkotunnus eli domain-nimi on merkkijono, joka ohjataan internetissä tiettyyn IP-osoitteeseen eli palvelimelle. Esimerkiksi www.iso.org

## Viittaukset
[1] GS1, ”Recommendation for the use of EPC and ISO RFID symbols,” 2022.  
[2] ISO/IEC, ”29160:2020. Information technology — Radio frequency identification,” 2020.  
[3] ISO, ”Online Browsing Platform (OBP): ISO 7000-3010,” 12 Maaliskuu 2010. [Online]. Available:https://www.iso.org/obp/ui#iso:grs:7000:3010. [Haettu 28 Lokakuu 2024].  
[4] GS1, ”GTIN Management Guideline for Construction Products,” Tammikuu 2023. [Online]. Available:https://www.gs1.org/standards/gtin-management-guideline-construction-products/current-standard#2-GTIN-Management-Rule-examples-for-construction-products+2-2-Declared-formulation-or-functionality.  
[5] GS1, ”GS1 Application Identifiers,” 2024. [Online]. Available: https://ref.gs1.org/ai/. [Haettu Syyskuu 2024].  
[6] G. Norway, ”Guideline for Unique identification of products with SGTIN (serialized GTIN). Labelling with GS1Datamatrix barcode and tagging with EPC / RFID Gen 2 UHF RFID tags,” 2018.  

## Liite 1
![20250109_BETK Soveltamisohje_Tuoteyksilöinti ja -tunnistaminen (1)_1](https://github.com/user-attachments/assets/a815804d-46ae-49bf-bf53-827eaab8e0c9)
## Asiakirjan tiedot

### Asiakirjan versio
| **Versio**| **Päivämäärä**| **Tekijä**  |**Muutoskuvaus**               |
|-----------|---------------|-------------|-------------------------------|
| 1.0       | 2024-12-10    |TAla         |Asiakirja julkaistu            |
| 1.1       | 2024-12-16    |TAla         |Lisätty puuttuvia tietoja ja korjattu kirjoitusvirheitä |
| 1.2       | 2025-01-09    |TAla         | Lisätty puuttuvia tietoja ja korjattu kirjoitusvirheitä |

### Asiakirjan laatijat

| **Nimi**            | **Organisaatio**     | **Contribution**               |
|---------------------|----------------------|--------------------------------|
| Teemu Alaluusua     | Aalto-yliopisto      |1st author                      |
| Juuso Autiosalo     | Aalto-yliopisto      |tuotti & editoi tekstiä         |
| Petri Leppänen      | GS1 Finland Oy       |tuotti & editoi tekstiä         | 
| Tom Partanen        | Consolis Parma Oy    |tuotti & editoi tekstiä         |
| Eetu Lahtinen       | Consolis Parma Oy    |tuotti elementtisuunnitelmakuvan|

## Asiantuntija ryhmä
| Nimi               | Organisaatio                   |
|--------------------|--------------------------------|
| Janne Kihula       | Rakennustuoteteollisuus RTT ry |
| Veijo Artoma       | Consolis Parma Oy              |
| Kari Turunen       | Lujabetoni Oy                  |
| Ville Retulainen   | Lujabetoni Oy                  |
| Markku Räisänen    | Betset Oy                      |
| Otto Alhava        | Fira Oy                        |
| Tuomas Kekki       | Fira Oy                        |
| Hannes Ilveskoski  | Fira Oy                        |
| Antti Pekkala      | Fira Oy                        |
| Ari Törrönen       | NCC Suomi Oy                   |
| Riku Laiho         | NCC Suomi Oy                   |
| Arto Nieminen      | NCC Suomi Oy                   |
| Janne Makkonen     | Consti                         |
| Ville Siikaoja     | YIT                            |
| Lassi Saari        | YIT                            |
| Klaus Turhanen     | RFID Lab Finland ry            |
| Janne Raitaniemi   | Riffid Oy                      |
| Juha Porkka        | Nordic ID Oyj                  |
| Sami Saari         | Rakennustieto Oy               |
| Teemu Rantanen     | Rakennustieto Oy               |








