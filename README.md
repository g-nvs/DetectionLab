# Detection Lab

## Objective

The Detection Lab project aimed to establish a controlled environment for simulating and detecting cyber attacks. The primary focus was to ingest and analyze logs within a Security Information and Event Management (SIEM) system, generating test telemetry to mimic real-world attack scenarios. This hands-on experience was designed to deepen understanding of network security, attack patterns, and defensive strategies.

### Skills Learned

- Advanced understanding of SIEM concepts, practical application and Wazuh architecture.
- Proficiency in analyzing and interpreting network logs.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.
- Tuning up of IDS and Agents default Rules to narrow down false positives.
- Understanding and creation of Custom Rules in Wazuh, for specific log ingestion in the System.

### Tools Used

- Wazuh for log centralization, ingestion and analysis.
- Network analysis tools (such as Wireshark) for capturing and examining network traffic.
- Telemetry generation tools to create realistic network traffic and attack scenarios.
- Sysmon for detailed information about process creations, network connections and real time changes to filesystem in Windows endpoints.
- Suricata configured as an IDS, for real-time threat detection and threat hunting.
- Zeek for a comprehensive view and analysis of the network activity. It allows to supplement Suricata logs.

## Steps

![Dashboard](https://github.com/user-attachments/assets/76ffab8b-f12f-4fc2-ad92-37002adc3653)
*Ref 1: Threat Hunting Dashboard*

![lsass_cred_dump_detection](https://github.com/user-attachments/assets/f332e549-ce21-4849-94e5-9ac3edf933e9)
*Ref 2: LSASS Dump Detection*

1. Provision the SIEM VM in Proxmox with the correct NW configuration.
2. Installation of all 3 Wazuh components in one VM.
3. FW Rules adjustment to let agents transferring telemetry data.
4. Provision of the IDS VM in Proxmox with the correct NW configuration and an addtional vNIC for Network TAP.
5. Installation and configuration of Suricata.
6. Configuration of a Soft-TAP service with daemonlogger in Proxmox to forward all traffic to Suricata VM. (Planning on change this and apply Port Mirroring directly with the Managed Switch later)
7. Suricata event forwarding to Wazuh with the Wazuh agent.
8. Provision of the NSM VM in Proxmox with the correct NW configuration and an addtional vNIC for Network TAP.
9. Installation and configuration of Zeek.
10. Configuration of a Soft-TAP service with daemonlogger in Proxmox to forward all traffic to Zeek VM.
11. Zeek event forwarding to Wazuh with the Wazuh agent.
    

