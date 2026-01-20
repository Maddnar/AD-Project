# AD-Project

## Objective
The objective of this project was to design and connect a multi–virtual machine lab environment to evaluate security monitoring and detection capabilities. This included establishing secure connectivity between Windows and Linux systems, performing attacks from a Kali Linux host, and analyzing the resulting telemetry in Splunk. The project also incorporated Atomic Red Team to simulate techniques mapped on the MITRE ATT&C and assess SIEM visibility, detection coverage, and potential monitoring gaps.

### Skills learned

- Built and managed a multi-VM lab environment with Windows, Linux, and Active Directory, including NAT networking and domain joining (Identify / Protect).
- Installed Splunk Enterprise on Ubuntu and deployed Universal Forwarder on Windows to centralize telemetry for analysis (Detect).
- Created custom Splunk searches to analyze user activity and account events, validating detection coverage (Detect / Respond).
- Executed Atomic Red Team simulations mapped to MITRE ATT&CK techniques (T1136.001, T1059.001) to test SIEM visibility (Detect / Respond).
- Identified a SIEM detection gap in PowerShell execution flags and proposed alerting improvements (Respond).
- Simulated controlled security events with Kali Linux to evaluate detection coverage and SIEM responsiveness (Detect / Respond).
- Planned and documented lab architecture and workflows, including VM setup, AD configuration, and SIEM integration (Govern / Identify).

### Tools Used

- **Virtualization**: Oracle VirtualBox
- **Operating Systems**: Windows 10, Windows Server 2019, Ubuntu Linux, Kali Linux
- **Security & Monitoring**: Splunk Enterprise, Splunk Universal Forwarder, Hydra on Kali Linux, Atomic-RedTeam


## Lab Architecture

<img src="images/Active_Directory_Project_Diagram.png" align="left" width="600"/>

The lab environment consisted of four virtual machines connected via a NAT network in VirtualBox. Each VM was assigned a specific role to support Active Directory, log collection, and security simulation. <p style="margin-left: 2em;"> 
   The diagram to the left shows the network architecture that I made on Draw.io. The dotted lines coming from the Windows 10 machine and Windows Server indicate their connection to the Splunk server via the Splunk Universal forwarder. The lab consisted of four virtual machines connected through a NAT network configured in VirtualBox. The Windows server hosted the Active Directory and DNS services, while the Windows 10 VM acted as a client as well as a target for the Kali Linux machine. Ubuntu ran the Splunk server for event log collection.
</p>

<br clear="left"/>

*Figure 1: VirtualBox NAT-based network connecting AD, endpoint, SIEM, and Kali Linux.*

## System Configuration and Virtual Machine Setup

