# **Introduction**

In this exercise, you will learn how to onboard a new Trading Partner by using the following capabilities of the Integration Suite:\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;• Integration Advisor\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;• Trading Partner Management\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;• Cloud Integration

   To make this session a successful one for all attendees, we recommend a good understanding of data structures (e. g. IDoc, SOAP, X12 or EDIFACT) along with some understanding of SAP Integration Suite capability Cloud Integration. The business process we will simulate in this exercise is part of the procure-to-pay process. The complete procure to pay consists of three transactions:\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;•	Purchase Order Request (Two-way transaction)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;•	Shipment Notification\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;•	Invoice Message

Here we focus on the first transaction. 

   To make things easier no additional installations (like postman) are necessary. The EDIFACT ORDERS will be sent from an iFlow which acts as a simulator of the Trading Partner. There is also no real S/4HANA system connected but another iFlow which receives the IDoc Orders Message and responds with an ORDRSP IDoc sent via Process Direct to TPM. After TPM has handled the message again a simulated Trading Partner receives the ORDRSP message as an EDIFACT message over AS2 and sends the message to your personal mail inbox that you can verify.

   To make exercise 1 easy, you will reuse already defined MIGs and MAGs. In the following exercises you will then create your own MIG and MAG. You simulate it to check if your mapping creates the expected results to use it in your transaction.
   
   [Continue to Exercise 1](exercises/Ex01/1/README.md)
