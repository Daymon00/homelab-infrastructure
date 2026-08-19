
<img width="831" height="542" alt="image" src="https://github.com/user-attachments/assets/06ef7880-8c78-4ac4-9770-ec017aa965b4" />


Proxmox VM design: 4 vCPU / 8 GB RAM / 80 GB disk
Why I created a dedicated wazuh01 VM
Ubuntu Server installation
<img width="1443" height="899" alt="image" src="https://github.com/user-attachments/assets/7f5678ce-509f-4208-b8d0-6624d6710988" />
Network configuration
<img width="1444" height="893" alt="image" src="https://github.com/user-attachments/assets/0f3c297a-6902-4c35-8e1d-048e058f6767" />
Interface: ens18
Address: 192.168.8.X/24
Assignment: DHCP
Network device: VirtIO

<img width="1429" height="897" alt="image" src="https://github.com/user-attachments/assets/352e7d5a-2b39-4dc0-9ff2-fbea304f1fa3" />
Confirming Storage
<img width="1448" height="896" alt="image" src="https://github.com/user-attachments/assets/bbcf0128-d7f3-4026-96f1-ca6262895e16" />
Configured the Wazuh VM with an 80 GB virtual disk using LVM, allocating 70 GB to the root filesystem and leaving additional free LVM space for future expansion.
<img width="1445" height="897" alt="image" src="https://github.com/user-attachments/assets/8e3adb56-d63e-4897-874e-6c3b2832a2aa" />
Enabled OpenSSH Server during Ubuntu installation to allow secure remote administration of the Wazuh VM.
<img width="1436" height="897" alt="image" src="https://github.com/user-attachments/assets/a0637793-4a45-42cd-8fdc-8ff51ced7377" />
Skipped optional server snaps to keep the Wazuh VM minimal.

Wazuh manager/indexer/dashboard installation

Adding Windows Server and Ubuntu agents

File Integrity Monitoring

Windows Event Log monitoring

Failed-login detection

Vulnerability detection

MITRE ATT&CK mapping

Custom detection rules

Problems and Solutinos

Screenshots of dashboards/alerts after everything works

Verify that Wazuh is actually receiving events
