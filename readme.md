# Implementing network security in compliance with ISO:IEC 27002:2013 in a LAN environment, based on selected technical controls.
# Concept 


This project will focus on implenting a small network infrastructure for a XYZ company that will be compliant with the ISO:IEC 27002:2013 standard. This implementation will focus only on selected technical controls that are related as close as possible to the network security field (e.g.: Access control, Cryptography, Asset Management, Asset Management). 
Most of the hardware components used in this topology are manufactured under the CISCO brand, nonethless other security products (such as IPS, IDS, NIDS, HIDS etc.) may be from another vendor. The idea of this work is to not focus on a specific vendor but rather to present the concept of implementing a small network in accordance with the above mentioned ISO standard.

ISO/IEC 27002 is an information security standard, part of the ISO/IEC 27000 family of standards, of which the last version was published in 2013.

The following security domains are covered by the ISO standard:
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
- A.9: Access control (14 controls)
- A.10: Cryptography (2 controls)
- A.12: Operations security (14 controls)
- A.14: System acquisition, development and maintenance (13 controls)

Access control:
- User access to corporate IT systems, networks, applications and information must be controlled in accordance with access requirements specified by the relevant Information Asset Owners, normally according to the user's role.
- Generic or test IDs must not be created or enabled on production systems unless specifically authorized by the relevant Information Asset Owners.
- After a predefined number of unsuccessful logon attempts, security log entries and (where appropriate) security alerts must be generated and user accounts must be locked out as required by the relevant Information Asset Owners.
- Passwords or pass phrases must be lengthy and complex, consisting of a mix of letters, numerals and special characters that would be difficult to guess.
- Passwords or pass phrases must not be written down or stored in readable format.
- Authentication information such as passwords, security logs, security configurations and so forth must be adequately secured against unauthorized or inappropriate access, modification, corruption or loss.
- Privileged access rights typically required to administer, configure, manage, secure and monitor IT systems must be reviewed periodically (at least twice a year) by Information Security and cross-checked by the appropriate departmental managers.
- Users must either log off or password-lock their sessions before leaving them unattended.
- Password-protected screensavers with an inactivity timeout of no more than 10 minutes must be enabled on all workstations/PCs.
- Write access to removable media (USB drives, CD/DVD writers etc.) must be disabled on all desktops unless specifically authorized for legitimate business reasons.



*The reason for this is that policies such as "Human Resource security" do not have controls that could colerate with network security.* 

