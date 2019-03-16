# Implementing chosen technical controls in compliance with NIST Cybersecurity Framework standard to achieve a secure network environment. 

# Concept 

This project will focus on implementing a small network infrastructure for a XYZ company that will be compliant with NIST Cybersecurity Framework. This implementation will focus only on selected technical controls that are related as close as possible to the network security field (e.g.: Access control, Data Security, Security Continuous Monitoring). 

The network presented in this publication will consist of the following devices (the number of devices might be a subject to change):

- x number of routers
- x number of switches
- x number of hosts (unix based mainly)
- x number of servers (ubuntu LTS)
- x number of Firewalls (pfSense open-source firewall) 
- x number of NIDS (SNORT and Suricata appliances)

The LAB will be created with EVE-NG Community Edition (the Emulated Virtual Environment for Network, Security and DevOps professionals). 
EVE-NG is a clientless multivendor network emulation software. 
The EVE-NG is available at https://www.eve-ng.net/

Most of the hardware components used in this topology are manufactured under the CISCO brand, nonethless other security products (such as IPS, IDS, NIDS, HIDS etc.) may be from another vendor. The idea of this project is to not focus on a specific vendor equipment but rather to present the idea of securing a simple network in accordance with the NIST Cybersecurity Framework, which should guarantee the basic-level of compliance with the information security standards such as ISO/IEC. Additionally, once all the below technical controls are implemented in our infrastructure, an audit will be performed to show that the network is somehow secure. The audit will have a holistic approach as we will try to find out what was implemented properly and what could have been implemented in a better way. This although does not mean that the audit will not find any issues, mainly due to the fact that we will be implementing only selected controls - the ideal result will be when our audit has some findings of various severities. 


The following control categories will be in the focus of our interest and the network will be implemented in a way to be compliant with: 

1. Risk Assessment (ID.RA): The organization understands the cybersecurity risk to organizational operations (including mission, functions, image, or reputation), organizational assets, and individuals.

2. Identity Management, Authentication and Access Control (PR.AC): Access to physical and logical assets and associated facilities is limited to authorized users, processes, and devices, and is managed consistent with the assessed risk of unauthorized access to authorized activities and transactions.

3. Data Security (PR.DS): Information and records (data) are managed consistent with the organization’s risk strategy to protect the confidentiality, integrity, and availability of information.

4. Protective Technology (PR.PT): Technical security solutions are managed to ensure the security and resilience of systems and assets, consistent with related policies, procedures, and agreements.

5. Anomalies and Events (DE.AE): Anomalous activity is detected and the potential impact of events is understood.

6. Security Continuous Monitoring (DE.CM): The information system and assets are monitored to identify cybersecurity events and verify the effectiveness of protective measures.

And from those control categories, we will focus only the following technical controls that we will cover in this project: 
*Please be informed that the idea is to implement the technical controls and no focus will be made on things such as 'implementing processes and people' etc. The framework states that there should be People, Processes and Technology to maintain a secure environment but our scope focuses only on the technology aspect.*

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


Mapping the controls to our infrastructure (where possible): 

- PR.AC-5: Network integrity is protected (e.g., network segregation, network segmentation)
- DE.AE-1: A baseline of network operations and expected data flows for users and systems is established and managed

In order to achieve proper network segmentation:

The network will operate as four zones, to maintain the confidentiality of data. 
- RED zone (external network, outside the company)
- ORANGE zone (DMZ, where honey pots, ftp and web servers reside)
- GREEN zone (intranet)
- BLUE zone (critical internal infrastructure), 


Only the following connections will be allowed: 
- RED zone <-> GREEN zone connections are allowed and should traverse through the ORANGE (DMZ) zone.
- BLUE <- GREEN connections are allowed.
- BLUE <-> ORANGE and BLUE <> RED are not allowed.

Blue zone will only receive ingress traffic from the green zone (to get the LOGS from IDS,NIDS,HIDS,IPS, NetFlow etc.).
The egress traffic will be disabled - the firewall between Green and Blue zone will only allow incoming traffic. This way we will assure that the data collected in blue-zone cannot be modified from the outside and can be assessed only on-site and locally. 

Each zone will have it's own VLAN. Two separate VLANs must communicate through a layer-3 device, therefore the switches between the zone will be either Layer-3 or we will place a router instead. 

- DE.CM-8: Vulnerability scans are performed
- ID.RA-1: Asset vulnerabilities are identified and documented

A vulnerability scans will be performed using Nmap, Nessus, OpenVAS. The scan results will be documented and assessed (i.e.: the possible impact of every found vulnerability will be rated and explained, ideally a risk scenario will be created). 

- PR.DS-6: Integrity checking mechanisms are used to verify software, firmware, and information integrity

To verify the integrity of data (e.g.: configuration files of network devices, SIEM logs) we will be using OSSEC HIDS. 
This Host Based Intrusion Detection System software can be found at https://www.ossec.net/ and is available for Windows and Unix architecture. 

We will be deploying OSSEC HIDS on the server that will be located in blue zone to guarantee the integrity of logs. 


- DE.CM-7: Monitoring for unauthorized personnel, connections, devices, and software is performed

A nmap script will be run multiple times once a day to look for unauthorized devices within the network. 
Basically we will be doing something like nmap -sP 192.168.0.1-100.

A document will be created that will list the company assets (i.e.: network devices and their hardware identifiers, MAC adresses).
This will help to keep track of devices that are allowed into the network. 

- DE.AE-2: Detected events are analyzed to understand attack targets and methods
- DE.AE-3: Event data are collected and correlated from multiple sources and sensors
- DE.CM-1: The network is monitored to detect potential cybersecurity events
- DE.CM-2: The physical environment is monitored to detect potential cybersecurity events
- DE.CM-4: Malicious code is detected

To collect and correlate the data from multiple sources we will use OSSIM open-source SIEM. 
The pfSense appliances will be also running SNORT in the background to log the network traffic and those will be one of the data sources that will be feeding the SIEM. Apart from that all the switches, routers and hosts will be reporting directly to the SIEM. The events and alerts will be determined during the next phase of the project. 
Snort (https://www.snort.org/) will be loaded with the community custom rules.

- PR.DS-1: Data-at-rest is protected
Servers and hosts will be hardened using Lynis (Lynis - Security auditing tool for Linux) and Tiger - The UNIX Security audit and intrusion detection tool. 


Short summary of used technologies and tools:
- Eve-NG, Snort , Suricata, OSSIM, OSSEC, pfSense, Cisco Layer 2/3 switches, Cisco routers, nmap, openVAS, tcpdump, Nessus, Kali Linux, Lynis, Tiger. 

The list of technologies may be expanded further during the project. 

The firewalls that we will use between network zones (e.g.: between DMZ and Green zone) will be running a pfSense appliance. PfSense can be easily integrated with SNORT - SNORT comes as a package that you can launch directly from the pfSense GUI. 

pFSense is also easily emulated on the EVE-NG environment. 

# Running pfSense on EVE-NG#
1. First, we will have to download the pfSense image from their official repository. (https://nyifiles.pfsense.org/mirror/downloads/pfSense-CE-2.3.5-RELEASE-2g-amd64-nanobsd.img.gz) 
2. Unzip it using zcat (if running unix box) zcat pfsense.img.gz > pfsense.img
3. SSH to the EVE-NG appliance and create directory for pfSense nodemkdir  mkdir /opt/unetlab/addons/qemu/pfsense-CE-2.3.5/
4. Upload the img to the above path
5. convert to qcow2 format cd /opt/unetlab/addons/qemu/pfsense-CE-2.3.5/ mv pfSense-CE-2.3.5-RELEASE-2g-amd64-nanobsd.img hda.qcow2
6. Set permissions /opt/unetlab/wrappers/unl_wrapper -a fixpermissions


# Running Cisco iOS switches (L2 or L3) 
https://www.eve-ng.net/documentation/howto-s/62-howto-add-cisco-iou-iol

# Running Cisco Routers based on dynamips
https://www.eve-ng.net/documentation/howto-s/64-howto-add-dynamips-images-cisco-ios

# Running Linux boxes
https://www.eve-ng.net/documentation/howto-s/106-howto-create-own-linux-image

In our project we will be using the following linux images
- Linux Kali 2018.1-amd64
- Linux Ubuntu server 14.04.4
- Linux Ubuntu desktop 17.10.1
- Linux TinyCore-6.4

# Summary
Further technical details or implementation how-to's will be explained and described during the next phase of the project which includes the practical phase. 
