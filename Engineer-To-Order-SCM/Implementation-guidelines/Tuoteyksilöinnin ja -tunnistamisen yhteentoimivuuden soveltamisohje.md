# Tuoteyksilöinnin ja -tunnistamisen yhteentoimivuuden soveltamisohje

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

| Taso | Kuvaus | Tunniste |
|------|--------|----------|
| 1 | Tuoteryhmä / Perustuote | GTIN |
| 2 | Tuotevariaatio | GTIN + MTO Varianttinumero |
| 3 | Tuoteyksilö | GTIN + (MTO Varianttinumero) + Sarjanumero (SGTIN) |

### 3.1 GS1-sovellustunnusten käyttäminen ETO-tuotteiden yksilöintiin

GS1-sovellustunnukset (AI = Application Identifiers) ovat numeerisia etuliitteitä, joita käytetään viivakoodeissa ja EPC/RFID-tunnisteissa määrittämään tietoelementtien merkitys ja muoto. GS1-sovellustunnusten käyttö mahdollistaa eri tietoelementtien erottamisen toisistaan viivakoodeissa tai EPC/RFID-tunnisteessa. GS1-standardi kattaa yli 100 sovellustunnusta. Jokainen sovellustunniste on oletusarvoisesti kaksi-, kolmi- tai nelinumeroinen luku. Listaus kaikista GS1-sovellustunnuksista on saatavilla GS1:n verkkosivuilla osoitteessa: [https://ref.gs1.org/ai/] .

Betonielementin yksilöinnissä minimitietovaatimuksissa tarvittaviksi GS1-sovellustunnuksiksi on tunnistettu seuraavat: (01) GTIN, (242) Made-to-Order variation number ja (21) Serial number. GS1-standardissa ei ole kansalliselle Elementtitunnukselle, GUID:lle ja verkkotunnukselle omaa GS1-sovellustunnusta, joten niiden sisällyttämisessä tiedonkantajaan on BETK-projektissa päätetty käytettävän sovellustunnuksia (91) Company interal information, (92) Company internal information ja (99) Company internal information. Numerolla 9 alkavia GS1-sovellustunnuksia käytetään vain silloin, mikäli kyseiselle tiedolle ei ole (vielä) määritetty omaa GS1-sovellustunnustaan. Huom! Verkkotunnuksen käsittely RFID-tunnisteissa on tämän ohjeen julkaisuhetkellä käsiteltävänä GS1:n kansainvälisessä standardinkehityksessä. Tuleva standardi ei välttämättä vastaa tässä esitettyä ratkaisua, mutta ohjeistus tullaan päivittämään standardin valmistuessa sen mukaiseksi. Optisessa tunnistamisessa (esim. QR-koodi) tämän tiedon sisällyttämisessä käytetään GS1 Digital Link URI syntax 1.5.0 -standardin mukaista menettelyä.

#### Minimitietovaatimukset tilauksesta suunniteltavien (ETO) rakennustuotteiden yksilöintiin
| AI | Tieto | Esimerkki |
|----|-------|-----------|
| (01) | GTIN-koodi | 06400001000247 |
| (242) | MTO varianttinumero | 123456 |
| (21) | Sarjanumero | 12345678910 |

Valinnaiset lisätiedot:

| AI | Tieto | Esimerkki |
|----|-------|-----------|
| (91) | Elementtitunnus | V1001 |
| (92) | GUID | ba34cf17-0c4b-4c6f-9295-cae05aa74ad4 |
| (99) | Verkkotunnus | id.rt.fi |
