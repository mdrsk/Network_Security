# Network_Security

Implementing network security of a small company in compliance with ISO:IEC 27001:2013.

This project will focus on implenting a small network infrastructure for a XYZ company that will be compliant with the ISO:IEC 27001:2013 document. Most of the hardware components used in this topology are manufactured under the CISCO brand, nonethless other security products (such as IPS, IDS, NIDS, HIDS etc.) may be from another vendor. The idea of this work is to not focus on a specific vendor but rather to present the concept of implementing a small network in accordance with the above mentioned ISO standard.

ISO/IEC 27001 is an information security standard, part of the ISO/IEC 27000 family of standards, of which the last version was published in 2013.

The following security domains are covered by the ISO standard:
A.5: Information security policies (2 controls)
A.6: Organization of information security (7 controls)
A.7: Human resource security - 6 controls that are applied before, during, or after employment
A.8: Asset management (10 controls)
A.9: Access control (14 controls)
A.10: Cryptography (2 controls)
A.11: Physical and environmental security (15 controls)
A.12: Operations security (14 controls)
A.13: Communications security (7 controls)
A.14: System acquisition, development and maintenance (13 controls)
A.15: Supplier relationships (5 controls)
A.16: Information security incident management (7 controls)
A.17: Information security aspects of business continuity management (4 controls)
A.18: Compliance; with internal requirements, such as policies, and with external requirements, such as laws (8 controls)

The four pillars of compliance: 
-> Integrity - Data cannot be modified, deleted or altered by unauthorized people, both in transit and at rest. 
The results of breaching the integrity part of data could have a significant impact. 

Imagine the following scenario:
User A: external user, no specific access rights, can only browse the website
User B: Internal user, super-admin, can edit the server files

User A is browsing the website of his bank website called BANK.com

If due to any reasons the User A could all of a sudden modify the server files, he could mess with the data of ongoing transactions, modify the account balances, delete user accounts or create new ones that could act as a backdoor. 

-> Confidentiality - Data must be presented only to the authenticated and authorized users. 

Scenario:
User A is working in financial institution as an IT Helpdesk person. 
User A gets a call from User B (person responsible for stock trading) to help him diagnose some issues with the e-mail exchange program.
User A remotely logs into the computer of User B and sees a lot of confidential e-mails present on the screen, containing bank account data, wealth data, name and surname of the clients etc. 

This could result not only in some potential risks related to the insider trading, data leakage, breaching the need-to-know policy and similiar but also in breaching the compliance of rules imposed by financial regulators.


-> Availabilityv - Data must be available to the users at all time. 
Scenario:
User A wants to sell his company stocks on a stock exchange via their website but the system has been taken offline by an ongoing DDoS attack. 
User A is not able to log-in and notify the system that he wants to sell the shares. 

As a result, customer is not able to sell his stocks and the next day the price went down causing a massive financial loss. 

-> Audit/Logging - Data must be logged in order to be available for review for example by a regulatory authority, external audit or internal audit. 

All access to the data should be logged at all time. The logs can be used for providing digital forensic evidence or to determine who was accessing which data at what time.

