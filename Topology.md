# Network_Security

Network topology


The network presented in this publication will consist of the following devices:
- x number of routers</br>
- x number of switches
- x number of hosts
- x number of servers
- x number of Firewalls
- x number of NIDS (SNORT appliance)

The logical topology of the network will look as presented in topology.png file.

There will be the following network zones:
- RED zone (external network, outside the company)
- ORANGE zone (DMZ, where honey pots, ftp and web servers reside)
- GREEN zone (intranet)
- BLUE zone (critical internal infrastructure)

The connections will be allowed as follows:  

- RED zone <> GREEN zone connections are allowed and should traverse through the ORANGE (DMZ) zone. 
- BLUE <> GREEN connections are allowed.
- BLUE <> ORANGE and BLUE <> RED are not allowed. 
- Blue zone will only receive ingress traffic from the green zone (to get the LOGS from snort for example)

For firewalls we will use pfSense appliances. 

For NIDS (Network Intrusion Detection System) we will be using SNORT appliances. 

SNORT vs Suricata - to decide

Snort is an open-source, lightweight, free network intrusion detection system (NIDS) software for Linux and Windows to detect emerging threats. It’s capable of of performing real-time traffic analysis and packet logging on IP networks.

