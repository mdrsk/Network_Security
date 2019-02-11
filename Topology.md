# Network_Security

Network topology


The network presented in this publication will consist of the following devices:
- 1 number of routers</br>
- 2 number of switches
- 5 number of hosts
- 4 number of servers
- 2 number of Firewalls
- 1 number of NIDS (SNORT appliance)

The logical topology of the network will look as presented in topology.png file.

There will be three network zones:
- RED zone (external network, outside the company)
- ORANGE zone (DMZ, where honey pots, ftp and web servers reside)
- GREEN zone (intranet)
- BLUE zone (critical internal infrastructure)

The connections will be allowed as follows:  

- RED zone <> GREEN zone connections are allowed and should traverse through the ORANGE (DMZ) zone. 
- BLUE <> GREEN connections are allowed.
- BLUE <> ORANGE and BLUE <> RED are not allowed. 
