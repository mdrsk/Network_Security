# Network_Security

The CIA triad (confidentiality, Integrity and Availability) - Most important pillars that are necessary to fulfill the requirements of ISO standard.

The four pillars of compliance: 
- Integrity. Data cannot be modified, deleted or altered by unauthorized people, both in transit and at rest. 
The results of breaching the integrity part of data could have a significant impact. 

Imagine the following scenario:
- User A: external user, no specific access rights, can only browse the website
- User B: Internal user, super-admin, can edit the server files

User A is browsing the website of his bank website called BANK.com

If due to any reasons the User A could all of a sudden modify the server files, he could mess with the data of ongoing transactions, modify the account balances, delete user accounts or create new ones that could act as a backdoor. 

####
- Confidentiality. Data must be presented only to the authenticated and authorized users. 

Scenario:
- User A is working in financial institution as an IT Helpdesk person. 
- User A gets a call from User B (person responsible for stock trading) to help him diagnose some issues with the e-mail exchange program.
- User A remotely logs into the computer of User B and sees a lot of confidential e-mails present on the screen, containing bank account data, wealth data, name and surname of the clients etc. 

This could result not only in some potential risks related to the insider trading, data leakage, breaching the need-to-know policy and similiar but also in breaching the compliance of rules imposed by financial regulators.

####
- Availability. Data must be available to the users at all time. 
Scenario:
- User A wants to sell his company stocks on a stock exchange via their website but the system has been taken offline by an ongoing DDoS attack. 
- User A is not able to log-in and notify the system that he wants to sell the shares. 

As a result, customer is not able to sell his stocks and the next day the price went down causing a massive financial loss. 

- Audit/Logging. Data must be logged in order to be available for review for example by a regulatory authority, external audit or internal audit. 

##All access to the data should be logged at all time. The logs can be used for providing digital forensic evidence or to determine who was accessing which data at what time.

