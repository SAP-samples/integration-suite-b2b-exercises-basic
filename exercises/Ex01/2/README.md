# **EXERCISE 1A: CREATE NEW MIG**

In the next step you will create your own MIG. \
Your Trading Partner expects the following Order Response EDIFACT Message:\
UNB+UNOC:3+1234567890123:1+UNEDI_TP_E_P123456:1+231217:1500+000255++++1'
UNH+5220230+ORDRSP:D:02A:UN:DF0320'
BGM++0000347163'
DTM+97:20231004:102'
LIN+1+5'
QTY+21:8.000:PCE'
PRI+INV:5250.00'
CUX+7:USD'
LIN+2+5'
QTY+21:8.000:PCE'
PRI+INV:4400.00'
CUX+7:USD'
LIN+3+5'
QTY+21:8.000:PCE'
PRI+INV:4884.00'
CUX+7:USD'
LIN+4+5'
QTY+21:8.000:PCE'
PRI+INV:5300.00'
CUX+7:USD'
UNS+S'
UNT+19+5220230'
UNZ+1+000255'

Use that to create a MIG. The steps are finding the correct nodes in the MIG (like BGM, like DTM, like PRI, …). Then use qualifiers (I’ve marked in the payload the qualifiers in yellow).

Nodes (like QTY) which appear several times with the same qualifier will only be one time in the MIG (they have the cardinality 0..n). Don’t be scared- in the next presentation (after this exercise) you will learn more about the qualifiers and their andvantages.

Luckily there is now a brand new feature in the Integration Advisor to really help you in creating the qualifiers. This assistant is using the payload to find out which qualifiers are needed. You only need to select the correct ones. If you want to read more about this feature have a look here:Blog for payload based MIG creation

The nodes marked in grey will not be modeled in the MIG in this exercise.
