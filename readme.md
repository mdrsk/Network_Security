# Implementing chosen technical controls in compliance with NIST Cybersecurity Framework standard to achieve a secure network environment. 

# Concept 

This project will focus on implementing a small network infrastructure for a XYZ company that will be compliant with NIST Cybersecurity Framework. This implementation will focus only on selected technical controls that are related as close as possible to the network security field (e.g.: Access control, Data Security, Security Continuous Monitoring). 

The network presented in this publication will consist of the following devices (the number of devices might be a subject to change):

x number of routers
x number of switches
x number of hosts
x number of servers
x number of Firewalls
x number of NIDS (SNORT appliance)

Most of the hardware components used in this topology are manufactured under the CISCO brand, nonethless other security products (such as IPS, IDS, NIDS, HIDS etc.) may be from another vendor. The idea of this project is to not focus on a specific vendor equipment but rather to present the idea of securing a simple network in accordance with the NIST Cybersecurity Framework, which should guarantee the basic-level of compliance with the information security standards such as ISO/IEC. 


The following control categories will be in the focus of our interest: 

1. Risk Assessment (ID.RA): The organization understands the cybersecurity risk to organizational operations (including mission, functions, image, or reputation), organizational assets, and individuals.

2. Identity Management, Authentication and Access Control (PR.AC): Access to physical and logical assets and associated facilities is limited to authorized users, processes, and devices, and is managed consistent with the assessed risk of unauthorized access to authorized activities and transactions.

3. Data Security (PR.DS): Information and records (data) are managed consistent with the organization’s risk strategy to protect the confidentiality, integrity, and availability of information.

4. Protective Technology (PR.PT): Technical security solutions are managed to ensure the security and resilience of systems and assets, consistent with related policies, procedures, and agreements.

5. Anomalies and Events (DE.AE): Anomalous activity is detected and the potential impact of events is understood.

6. Security Continuous Monitoring (DE.CM): The information system and assets are monitored to identify cybersecurity events and verify the effectiveness of protective measures.

And from those control categories, we will focus on the following technical controls that we will cover in this project: 

- ID.RA-1: Asset vulnerabilities are identified and documented
- PR.AC-5: Network integrity is protected (e.g., network segregation, network segmentation)
- PR.DS-1: Data-at-rest is protected
- PR.DS-2: Data-in-transit is protected
- PR.DS-5: Protections against data leaks are implemented
- PR.DS-6: Integrity checking mechanisms are used to verify software, firmware, and information integrity
- PR.PT-1: Audit/log records are determined, documented, implemented, and reviewed in accordance with policy
- PR.PT-4: Communications and control networks are protected
- DE.AE-1: A baseline of network operations and expected data flows for users and systems is established and managed
- DE.AE-2: Detected events are analyzed to understand attack targets and methods
- DE.AE-3: Event data are collected and correlated from multiple sources and sensors
- DE.CM-1: The network is monitored to detect potential cybersecurity events
- DE.CM-2: The physical environment is monitored to detect potential cybersecurity events
- DE.CM-4: Malicious code is detected
- DE.CM-7: Monitoring for unauthorized personnel, connections, devices, and software is performed
- DE.CM-8: Vulnerability scans are performed




- PR.AC-5: Network integrity is protected (e.g., network segregation, network segmentation)

In order to achieve proper network segmentation:

The network will operate as four zones, to maintain the confidentiality of data. 
- RED zone (external network, outside the company)
- ORANGE zone (DMZ, where honey pots, ftp and web servers reside)
- GREEN zone (intranet)
- BLUE zone (critical internal infrastructure), 


Only the following connections will be allowed: 
RED zone <-> GREEN zone connections are allowed and should traverse through the ORANGE (DMZ) zone.
BLUE <- GREEN connections are allowed.
BLUE <-> ORANGE and BLUE <> RED are not allowed.

Blue zone will only receive ingress traffic from the green zone (to get the LOGS from IDS,NIDS,HIDS,IPS, NetFlow etc.).
The egress traffic will be disabled - the firewall between Green and Blue zone will only allow incoming traffic. This way we will assure that the data collected in blue-zone cannot be modified from the outside and can be assessed only on-site and locally. 






