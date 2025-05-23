# Tuoteyksilöinnin ja -tunnistamisen yhteentoimivuuden soveltamisohje

**Tilauksesta suunniteltavat rakennustuotteet**  
Julkaisija: Rakennusteollisuus ry
Julkaistu: 9.1.2025  
Versio: 1.2  
Status: Julkaistu

## Asiakirjan laatijat

| Nimi | Organisaatio |
|------|--------------|
| Teemu Alaluusua | Aalto-yliopisto |
| Juuso Autiosalo | Aalto-yliopisto |
| Tom Partanen | Consolis Parma Oy |
| Eetu Lahtinen | Consolis Parma Oy |
| Janne Kihula | Rakennustuoteteollisuus RTT ry |
| Veijo Artoma | Consolis Parma Oy |
| Kari Turunen | Lujabetoni Oy |
| Ville Retulainen | Lujabetoni Oy |
| Markku Räisänen | Betset Oy |
| Otto Alhava | Fira Oy |
| Tuomas Kekki | Fira Oy |
| Hannes Ilveskoski | Fira Oy |
| Antti Pekkala | Fira Oy |
| Ari Törrönen | NCC Suomi Oy |
| Riku Laiho | NCC Suomi Oy |
| Arto Nieminen | NCC Suomi Oy |
| Janne Makkonen | Consti |
| Ville Siikaoja | YIT |
| Lassi Saari | YIT |
| Klaus Turhanen | RFID Lab Finland ry |
| Janne Raitaniemi | Riffid Oy |
| Juha Porkka | Nordic ID Oyj |
| Petri Leppänen | GS1 Finland Oy |
| Sami Saari | Rakennustieto Oy |
| Teemu Rantanen | Rakennustieto Oy |

## 1. Tausta

Rakennustuotteiden yksilöinti ja tunnistaminen on merkittävimpiä osatekijöitä kiinteistö- ja rakennusalan digitalisaatiossa. Vakioidut, yhteentoimivat ja globaalisti käytetyt tuoteyksilöinnin ja -tunnistamisen menetelmät mahdollistavat eri toimijoiden välisen tiedonvaihdon yhtenäisellä tavalla.

GS1:n kehittämät toimitusketjun hallinnan standardit, kuten GTIN ja EAN-viivakoodi, mahdollistavat yhtenäisen tiedonvaihdon toimitusketjun kaikissa vaiheissa.

## 2. Soveltamisohjeen tarkoitus

Tämä soveltamisohje on tuotettu osana Rakennusteollisuus RT:n kehityshanketta, ja sen tavoitteena on tukea rakennusalan toimitusketjun siirtymistä manuaalisesta ja rakenteettomasta tiedonvaihdosta täysin rakenteelliseen ja koneluettavaan tiedonvaihtoon.

Ohjeessa kuvataan malli GS1-standardien soveltamisesta tilauksesta suunniteltavien (ETO) rakennustuotteiden toimitusketjun hallintaan, erityisesti betonielementtien esimerkin kautta.

## 3. Rakennustuotteiden SGTIN-tuoteyksilöinti

Tuoteyksilöinti on edellytys toimitusketjun digitalisoinnille. BETK-työryhmässä on päädytty hyödyntämään GS1-standardia kolmella yksilöinnin tasolla:

| Taso | Kuvaus | Tunniste |
|------|--------|----------|
| 1 | Tuoteryhmä / Perustuote | GTIN |
| 2 | Tuotevariaatio | GTIN + MTO Varianttinumero |
| 3 | Tuoteyksilö | GTIN + (MTO Varianttinumero) + Sarjanumero (SGTIN) |
