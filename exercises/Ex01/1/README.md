**EXERCISE 1: SIMPLE ONBOARDING OF A NEW TRADING PARTNER**

**1. Create new Trading Partner**

Please logon https://opensapeu01.integrationsuite.cfapps.eu10-002.hana.ondemand.com/shell/home with your UserXX. The password you will get from the Trainers.

To make all entities unique we recommend adding your user id like TradingPartner-P123456 (if your userid is P123456). If your user is like UserXX so, please create then entities like TradingPartner-UserXX. In other words: please replace the “P” with “User” and the “123456” with your number. As all identifiers are compared as strings be very precise (especially with upper and lower case) there otherwise you will run into error messages.

![Test Image 4](https://github.com/SAP-samples/integration-suite-b2b-exercises-basic/blob/main/exercises/Ex01/1/assets/1.png)

![Test Image 4](https://github.com/SAP-samples/integration-suite-b2b-exercises-basic/blob/main/exercises/Ex01/1/assets/1.png)

**2. Use Agreement Template to create an agreement**

With the Agreement, you instantiate the agreement template where you need to fill out the details of the trading partners


**3. Prepare Simulation Flow and send a message**

As we have defined that the trading partner sends an EDIFACT Order via the AS2 Protocol we need to simulate this. Therefore, we have built an integration flow which you have to copy to a new package, configure it and deploy. The EDIFACT message is sent as soon as the integration flow is deployed.


**4. Monitor the Scenario**

The EDIFACT message is now sent to the generic integration flow and from there via the IDOC Adapter to the simulated S/4HANA system which generates an ORDRSP. This is then mapped to EDIFACT and sent as an email to your inbox. To monitor B2B Scenarios let’s have a look at the B2B Monitoring.
