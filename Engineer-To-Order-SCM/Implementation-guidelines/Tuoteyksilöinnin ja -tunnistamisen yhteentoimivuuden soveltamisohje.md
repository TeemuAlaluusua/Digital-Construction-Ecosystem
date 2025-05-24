# Tuoteyksilöinnin ja -tunnistamisen yhteentoimivuuden soveltamisohje

Here is a simple footnote[^1].
[^1]: My reference.

**Tilauksesta suunniteltavat rakennustuotteet**  
>Julkaisija: Rakennusteollisuus ry\
>Julkaistu: 9.1.2025  
Versio: 1.2  
Status: Julkaistu

## Asiakirjan laatijat

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

## 1. Tausta
Rakennustuotteiden yksilöinti ja tunnistaminen on merkittävimpiä osatekijöitä kiinteistö- ja rakennusalan digitalisaatiossa. Vakioidut, yhteentoimivat ja globaalisti käytetyt tuoteyksilöinnin ja -tunnistamisen menetelmät mahdollistavat eri toimijoiden välisen tiedonvaihdon yhtenäisellä tavalla, riippumatta toimitusketjun osapuolesta.

GS1:n kehittämät toimitusketjun hallinnan standardit, kuten tuoteyksilöintiin hyödynnettävä tuotetunnus GTIN yhdessä EAN-viivakoodin kanssa, mahdollistavat eri toimijoiden välisen tiedonvaihdon yhtenäisellä tavalla. GTIN tuotetunnuksen avulla voidaan siis tunnistaa mikä tahansa kauppatavara, joka voidaan hinnoitella, tilata tai laskuttaa missä tahansa toimitusketjun vaiheessa, josta on tarpeen hakea ennalta määritettyjä tietoja.

Kaupan alalla tuotteet on yksilöity GTIN-koodien ja koneluettavien 1D EAN-viivakoodien kautta jo yli 50 vuotta, ja nyt tämä toimiva käytäntö on vakiintunut myös varasto-ohjautuvien (MTS) rakennustuotteiden osalta. Suomalaisessa rakennusteollisuudessa hyödynnetään kuitenkin tilauksesta suunniteltavia tuotteita, joiden osalta käytettävät yksilöinnin ja tunnistamisen menetelmät eivät ole vakiintuneet. Rakennustuotteiden yksilöinti on tiedonvaihdon näkökulmasta tärkeää, sillä rakennustuotteiden käyttöikä on yleensä pitkä, ja jotkut niistä ovat aktiivisessa käytössä jopa yli 100 vuotta. Uusien materiaalien nopea kehitys sekä kestävyyden ja kiertotalouden kasvava merkitys ovat lisänneet tarvetta hallita rakennetuissa kohteissa käytettyjä rakennustuotteita ja niiden ominaisuuksia elinkaaren ajan.

## 2. Soveltamisohjeen tarkoitus
Tämä soveltamisohje on tehty osana Rakennusteollisuus RT:n tuotetiedon ja toimitusketjun digitalisoinnin kehityshanketta, BETK-työryhmän toimesta. Kehityshankkeen ensisijainen tavoite on edistää rakennusalan tuotteiden toimitusketjun hallinnan menetelmien siirtymistä manuaalisesta ja rakenteettomasta tiedonvaihdosta täysin rakenteelliseen ja koneluettavaan tiedonvaihtoon. Asiakirja on jatkuvasti päivittyvä ja sitä kehitetään edelleen Rakennusteollisuus RT:n kehityshankkeen havaintojen perusteella.

Soveltamisohje keskittyy toimitusketjun digitalisoinnissa tarvittavaan tuotteiden yksilöintiin ja koneelliseen tunnistamiseen. Soveltamisohjeessa kuvataan malli avointen GS1-standardien soveltamisesta tilauksesta suunniteltavien (ETO) rakennustuotteiden toimitusketjun hallintaan, käyttäen esimerkkinä betonielementtejä. GS1:llä on tilauksesta suunniteltavien ja valmistettavien tuotteiden yksilöintiin liittyen käynnissä kansainvälistä standardointityötä. Tämä soveltamisohje on tehty standardoinnin ollessa kesken, joten sitä tullaan tarvittaessa päivittämään myöhemmin.

## 3. Rakennustuotteiden SGTIN-tuoteyksilöinti
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





























