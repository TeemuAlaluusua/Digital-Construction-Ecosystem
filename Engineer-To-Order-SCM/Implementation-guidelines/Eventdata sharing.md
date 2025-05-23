# 🇫🇮 Tapahtumatiedon jakaminen GS1 EPCIS toimitusketjuhallinta standardin mukaan 
:building_construction::articulated_lorry:
Lähdeaineistot:
1. [EPCIS Sandbox](https://epcis-sandbox.gs1.org/)
2. [EPCIS Standard](https://ref.gs1.org/standards/epcis/)
3. [EPCIS and CBV Implementation Guideline](https://www.gs1.org/docs/epc/EPCIS_Guideline.pdf)
4. [Core Business Vocabulary (CBV) Standard](https://ref.gs1.org/standards/cbv/)
5. [Launch](https://www.gs1.org/docs/epcis/epcis_2-0_launch.pdf)


CBV Statukset raksalle

| Statustieto                 |Käyttötarkoitus        | Business step  | Disposition | moi            |
| --------------------------- | ----------------------| ----------     | ----------  | ----------     |
| Odottaa lähtötietoja        | awaiting_information  | Content Cell   |             |                |
| Lähtötiedot vastaanotettu   | information_received  | Content Cell   |             |                |
| Suunnittelu käynnissä       | Content Cell          | Content Cell   |             |                |
| designing                   | Content Cell          | Content Cell   |             |                |
| Odottaa lähtötietoja        |                       | designing      |             |                |
| Lähtötiedot vastaanotettu   |                       | designing      |             |                |
| Suunnittelu käynnissä       |                       | designing      |             |                |
|                             |                       |                |             |                |









## Suunnitteluvaihe

![20250515_Kuva1](https://github.com/user-attachments/assets/b700cd01-b8bd-4143-9abc-ecefd0af2573)



New CBV status proposals

| Business step | Definition                                                                                                                                                                                                                   |Example of use                                                                                                                                                                                     |
|---------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|*designing*    |Business-process of designing a product |An item instance is defined by initial data. Design process takes place before selecting or producing the produt                                                                     |An item instance is defined by initial data. Design process takes place before selecting or producing the produt                                                                                   |
|*design_change*|Denotes a specific activity within business process where a change in an already completed and published design/plan is in the making                                                                                         |In the producing process it is noticed that the original design/plan needs to be updated, so a request for update is made and and the update is in the making                                      |
|*producing*    |Denotes a specific activity within business process where a product is produced. Either from raw materials or other products. Can not be afterwards disassembled to identifiable products as in the business step: assembled  |In excample concrete elements                                                                                                                                                                      |
|*error*        |Denotes a business process where error takes place and actions are made to solve it. Could happen in any stage of the supplychain                                                                                             |The surface of the concrete element does not match the quality requirements. The main process flow continues and the element is installed in place. The repair is scheduled and will be done later |
