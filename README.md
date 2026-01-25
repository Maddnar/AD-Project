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

<img src="images/Active_Directory_Project_Diagram.png" align="left" width="700"/>

The lab architecture was designed to emulate a small enterprise network for identity management, monitoring, and attack simulation purposes. <p style="margin-left: 2em;"> 
   The lab environment consisted of four virtual machines connected through a NAT network in VirtualBox, with each system assigned a specific role to support Active Directory services, centralized log collection, and security testing. The network architecture, illustrated in the diagram created using Draw.io, shows dotted lines extending from the Windows Server and Windows 10 machines to the Splunk server, representing their connections through the Splunk Universal Forwarder. The Windows Server VM hosted Active Directory and DNS services, the Windows 10 VM functioned as a domain-joined client and attack target, the Ubuntu VM ran the Splunk server for event log aggregation, and the Kali Linux VM was used to simulate threat activity.
</p>

<br clear="left"/>

*Figure 1: VirtualBox NAT-based network connecting AD, endpoint, SIEM, and Kali Linux.*

## System Configuration and Virtual Machine Setup

I've worked with virtual machines extensively in the National Guard; however, most of those systems are pre-built and pre-configured to communicate upon startup. In contrast, this project required selecting, installing, and configuring each virtual machine manually to ensure proper network connectivity, service functionality, and role separation. When choosing operating systems, I prioritized compatibility with Active Directory, Splunk, and common security tools, as well as overall system stability. VirtualBox was selected as the hypervisor due to its accessibility and support for NAT networking, which allowed the virtual machines to communicate internally while maintaining isolation from the host network.

Due to hardware resource limitations on my laptop, the virtual machines were migrated to a desktop system with greater processing power and memory capacity. This ensured stable performance when running multiple virtual machines simultaneously, particularly during Active Directory operations, log forwarding, and security testing activities. The desktop environment allowed for smoother execution of services and reduced performance bottlenecks observed during initial testing on the laptop.

Each virtual machine was provisioned with appropriate CPU, memory, and storage resources based on its role. The Windows Server VM was configured with Active Directory Domain Services and DNS, the Windows 10 VM was joined to the domain, and the Kali Linux VM was prepared with standard penetration testing tools. The Ubuntu VM was configured to host the Splunk server, so I provisioned it with an extra CPU core and additional RAM, since it would be ingesting traffic from both the Windows server and the Windows client. Network settings were standardized across all machines to ensure consistent communication within the NAT network.

## Service Installation and Configuration

After the virtual machines were provisioned and network connectivity was verified, core services were installed and configured to support authentication, centralized logging, and security monitoring. This included deploying Active Directory Domain Services on the Windows Server, installing Splunk Enterprise on the Ubuntu system, and configuring Splunk Universal Forwarders on the Windows Server and Windows 10 machines to forward traffic logs to the SIEM. These configurations established the foundation for monitoring user activity and detecting malicious behavior.

### Active Directory Domain Services Setup

### Splunk Enterprise Install

### Splunk Universal Forwarder Install

### Endpoint Configuration
