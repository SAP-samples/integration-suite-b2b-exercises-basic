# **EXERCISE 1: SIMPLE ONBOARDING OF A NEW TRADING PARTNER**

## **1. Create new Trading Partner**

Please logon https://opensapeu01.integrationsuite.cfapps.eu10-002.hana.ondemand.com/shell/home with your UserXX. The password you will get from the Trainers.

To make all entities unique we recommend adding your user id like TradingPartner-P123456 (if your userid is P123456). If your user is like UserXX so, please create then entities like TradingPartner-UserXX. In other words: please replace the “P” with “User” and the “123456” with your number. As all identifiers are compared as strings be very precise (especially with upper and lower case) there otherwise you will run into error messages.

**Step 1**: Log on to the Integration Suite tenant with your system details provided to you by the app.
![image](https://github.com/SAP-samples/integration-suite-b2b-exercises-basic/blob/main/exercises/Ex01/1/assets/1.png)


**Step 2**: Navigate to Design and select B2B Scenarios.

**Step 3**: As you want to onboard a new Trading Partner switch to the tab Partner Profiles.

**Step 4**: Select Create->Trading Partner to create a new Trading Partner.

**Step 5**: On the following screen, you need to maintain general data for the new trading partner as follows:
Company Name: TradingPartner-P123456 (with P123456 your userid)
Company Short Name: TradingPartnerXX (with P123456 your user id)
All the other fields are optional.


Please save the newly created Trading Partner.


**Step 6**: Switch to the Contacts tab and select Create Contact

**Step 7**: On the Contacts tab, you can add names and details of persons who are responsible at the Trading Partner side.

**Step 8**: Navigate to the tab Identifier and create a Single Identifier.

**Step 9**: Every Trading Partner needs at least two identifiers: one which is used in the exchange and a second one which is used in the S/4 System.
Maintain the first identifier as follows:
Use Identification UNEDI_TP_E_P123456 (with P123456 your user id), the same for the alias,
select Type System 
UN/EDIFACT,
and Scheme Duns (Dun & Bradstreet),
then save the new identifier.


**Step 10**: Maintain the second Single Identifier as follows:
Use Identification O-P123456 (with P123456 your user id), the same as Alias, 
select Type System SAP S/4HANA on Premise IDoc,
and Scheme N/A,
then save the new identifier.

**Step 11**: In the security tab you need to add the partner ID which your trading partner will use to send the message. To make it simpler we use the same ID as in the step before.
O-P123456 (with P123456 your user id). Then save it.


**Step 12**: As the AS2 Partner ID also need to be pushed to the Partner directory you need to activate it by clicking the activate toggle button. 

**Step 13**: The Business Context is currently optional, but we need to create a system where the supported type system and communication details must be maintained.
Navigate to the tab System and select Create System.

**Step 14**: Please add the following Details:
Name B2B-System-P123456 (with P123456 your user id), B2B-System-P123456 (with P123456 your user id) as Alias,
Type B2B System,
Purpose Dev
and save the new system. 


**Step 15**: Select the beforehand created system to create the supported Type System. On tab Type System, select Create Type System.

**Step 16**: Use UN/EDIFACT and Version D.02A S3, then save the new Type System.

**Step 17**: Next, you need to maintain the communication details. Switch to tab Communication and select Create Communication.

**Step 18**: As this Trading Partner will send an Order via AS2 you need to create an AS2 Sender.
Use in the Security Configuration Mode Profile and the AS2 Partner ID you’ve configured under the security tab.

**Step 19**: As the backend will send an ORDRSP message back, you also need to create another communication as this should be received by the Trading Partner (which will forward it then to you via mail). To create that, you need first to find out the url of the simulated trading partner on your tenant.
For this first duplicate this tab to easily switch between screens, then navigate to the monitoring for Integrations and APIs


**Step 20**: Click on the tile with All.

**Step 21**: Search for B2B-Partner-Simulator and copy the url with the copy button. This url will end with .com/as2/as2.
Do not use the url from the screenshot as your tenant might be a different one than the tenant from the screenshot.


**Step 22**: Now jump back to TPM and there to your Trading Partner where you have to add another communication under the system tab.
Use the names as you can see in the screenshot.
For the recipient url you need to paste the url from the previous step.
Please switch then to Basic Authentication with the Credential ESB. 


**step 23**: Switch to the Tab Processing to enter to AS2 Ids, Subject and your mail address. Please use a mail address which works and where you can receive mails as the output will later be sent to that mail.
It is mandatory that the Own AS2 looks like OwnId-P123456 and the Partner AS2 Id like PartnerId-P123456 (both times with P123456 as your user id).  Please take care to keep the Uppercase/lowercase for the Ids as in the example! Then save the communication.




## **2. Use Agreement Template to create an agreement**

With the Agreement, you instantiate the agreement template where you need to fill out the details of the trading partners

**Step 1**: Navigate back to Design  B2B Scenarios, and switch to the tab Agreements.

**Step 2**: On the Agreements tab, create a new Agreement.

**Step 3**: In the upcoming dialog, select the existing Agreement [openSAP - BTP4] Procure to Pay B2B Template and select Next.

**Step 4**: 4.	Switch the Agreement Creation Mode to Copy from Template.
(more details can be found in the documentation https://help.sap.com/docs/integration-suite/sap-integration-suite/creating-trading-partner-agreement. Deselect Shipment Notification and Invoice Message as in this simplified example we are only using the Purchase Order Request Response. Then select the TradingPartner-P123456 (with P123456 your userid) you’ve created and click on Open Draft.

**Step 5**: Please start with renaming the Agreement to Procure to Pay – P123456 (with P123456 your user id) and change the Description. Now you need to specify which Trading Partner Details you want to use. Please enter these details in the following order (with P123456 your user id):
Maintain System B2B-System-P123456, Type System UN/EDIFACT, Type System Version D.02A S3, Identifier UNEDI_TP_E_P123456, and Identifier as Company O-P123456.
Finally, select the Identifier as Trading Partner 123456789123 from the drop-down.

Hint: use the drop-down help but start with the Trading Partner Details and select the Identifier as Trading Partner as the last one.
When done, save your settings.


**Step 6**: Navigate to the tab B2B Scenarios and switch the Transaction to the edit mode.

**Step 7**: There you see the transactions for the scenario. In our exercise, it is a two-way transaction initiated by the trading partner.

**Step 8**: Please start on the right by clicking on the first Communication box within the flow and select AS2 for Communication.

**Step 9**: Please click now on the Interchange box to define the Message Implementation Guideline. Select the drop-down list.

Note: The Message Implementation Guideline have been already prepared by using the Integration Advisor capability of SAP Integration Suite.


**Step 10**: In the pop up select openSAP BTP4 - EDIFACT ORDERS and switch to the highest version. Then select Choose.

**Step 11**: Last step for the definition of the Order is to select the Mapping box (which is also prepared by using the Integration Advisor). Select the drop-down list.

**Step 12**: In the pop up select openSAP BTP4 - EDIFACT ORDERS to IDoc ORDERS and switch to the highest version. Then select Choose.

**Step 13**: As the backend will also send an Order Response the necessary data for these needs also to be maintained. Select the Communication for the outgoing message to AS2.Receiver.


**Step 14**: Please click now on the Interchange box to define the Message Implementation Guideline. Select the drop-down list.

**Step 15**: In the pop up select openSAP BTP4 - EDIFACT ORDRSP and switch to the highest version. Then select Choose.

**Step 16**: Last step for the definition of the Order Response is to select the Mapping box Select the drop-down list

**Step 17**: In the pop up select openSAP BTP4 – Idoc ORDRSP to EDIFACT ORDRSP and switch to the highest version. Then select Choose.

**Step 18**: Save the Agreement

**Step 19**: Activate the agreement to write all necessary data into the Partner Directory Database.


## **3. Prepare Simulation Flow and send a message**

As we have defined that the trading partner sends an EDIFACT Order via the AS2 Protocol we need to simulate this. Therefore, we have built an integration flow which you have to copy to a new package, configure it and deploy. The EDIFACT message is sent as soon as the integration flow is deployed.


## **4. Monitor the Scenario**

The EDIFACT message is now sent to the generic integration flow and from there via the IDOC Adapter to the simulated S/4HANA system which generates an ORDRSP. This is then mapped to EDIFACT and sent as an email to your inbox. To monitor B2B Scenarios let’s have a look at the B2B Monitoring.
