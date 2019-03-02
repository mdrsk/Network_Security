# Implementing chosen technical controls in compliance with ISO:IEC 27001 standard to achieve a secure network environemnt. 

# Concept 


This project will focus on implementing a small network infrastructure for a XYZ company that will be compliant with A.9 domain and  of the ISO:IEC 27002:2013 standard. This implementation will focus only on selected technical controls that are related as close as possible to the network security field (e.g.: Access control, Cryptography, Asset Management, Asset Management). 
Most of the hardware components used in this topology are manufactured under the CISCO brand, nonethless other security products (such as IPS, IDS, NIDS, HIDS etc.) may be from another vendor. The idea of this work is to not focus on a specific vendor but rather to present the concept of implementing a small network in accordance with the above mentioned ISO standard.

ISO/IEC 27002 is an information security standard, part of the ISO/IEC 27000 family of standards.

The following security domains are covered by the ISO (27001/2 2013) standard:
- A.5: Information security policies (2 controls)
- A.6: Organization of information security (7 controls)
- A.7: Human resource security - 6 controls that are applied before, during, or after employment
- A.8: Asset management (10 controls)
- A.9: Access control (14 controls)
- A.10: Cryptography (2 controls)
- A.11: Physical and environmental security (15 controls)
- A.12: Operations security (14 controls)
- A.13: Communications security (7 controls)
- A.14: System acquisition, development and maintenance (13 controls)
- A.15: Supplier relationships (5 controls)
- A.16: Information security incident management (7 controls)
- A.17: Information security aspects of business continuity management (4 controls)
- A.18: Compliance; with internal requirements, such as policies, and with external requirements, such as laws (8 controls)


Our implementation will focus on those technical controls:
- A.10.5.1 Information back-up Control Back-up copies of information and software shall be taken and tested regularly in accordance with the agreed backup policy. 
- A.10.4.1 Controls against malicious code Control Detection, prevention, and recovery controls to protect against malicious code and appropriate user awareness procedures shall be implemented. 
- A.10.1.1 Documented operating procedures Control Operating procedures shall be documented, maintained, and made available to all users who need them.
- A.10.6.1 Network controls - Control Networks shall be adequately managed and controlled, in order to be protected from threats, and to maintain security for the systems and applications using the network, including information in transit.
- A.10.10.1 Audit logging Control Audit logs recording user activities, exceptions, and information security events shall be produced and kept for an agreed period to assist in future investigations and access control monitoring. 
- A.10.10.2 Monitoring system use Control Procedures for monitoring use of information processing facilities shall be established and the results of the monitoring activities reviewed regularly. 
- A.10.10.3 Protection of log information Control Logging facilities and log information shall be protected against tampering and unauthorized access.
- A.10.10.4 Administrator and operator logs Control System administrator and system operator activities shall be logged.
- A.10.10.5 Fault logging Control Faults shall be logged, analyzed, and appropriate action taken. 
- A.10.10.6 Clock synchronization Control The clocks of all relevant information processing systems within an organization or security domain shall be synchronized with an agreed accurate time source.
- A.11.4.1 Policy on use of network services Control Users shall only be provided with access to the services that they have been specifically authorized to use. 
- A.11.4.2 User authentication for external connections Control Appropriate authentication methods shall be used to control access by remote users. 
- A.11.4.3 Equipment identification in networks Control Automatic equipment identification shall be considered as a means to authenticate connections from specific locations and equipment. 
- A.11.4.4 Remote diagnostic and configuration port protection Control Physical and logical access to diagnostic and configuration ports shall be controlled.
- A.11.4.5 Segregation in networks Control Groups of information services, users, and information systems shall be segregated on networks. 
- A.11.4.6 Network connection control Control For shared networks, especially those extending across the organization’s boundaries, the capability of users to connect to the network shall be restricted, in line with the access control policy and requirements of the business applications.
- A.11.4.7 Network routing control Control Routing controls shall be implemented for networks to ensure that computer connections and information flows do not breach the access control policy of the business applications.
- A.11.5.1 Secure log-on procedures Control Access to operating systems shall be controlled by a secure log-on procedure. 
- A.11.5.2 User identification and authentication Control All users shall have a unique identifier (user ID) for their personal use only, and a suitable authentication technique shall be chosen to substantiate the claimed identity of a user.
- A.11.5.3 Password management system Control Systems for managing passwords shall be interactive and shall ensure quality passwords.
- A.11.5.4 Use of system utilities Control The use of utility programs that might be capable of overriding system and application controls shall be restricted and tightly controlled. 
- A.11.5.5 Session time-out Control Inactive sessions shall shut down after a defined period of inactivity. 
- A.11.5.6 Limitation of connection time Control Restrictions on connection times shall be used to provide additional security for high-risk applications.
- A.12.6.1 Control of technical vulnerabilities Control Timely information about technical vulnerabilities of information systems being used shall be obtained, the organization's exposure to such vulnerabilities evaluated, and appropriate measures taken to address the associated risk. 










