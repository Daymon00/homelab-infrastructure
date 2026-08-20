# Wazuh Setup

I wanted to add Wazuh to my homelab so I could get more hands-on experience with SIEMs, log monitoring, alerts, vulnerability detection, and endpoint security.

I decided to give Wazuh its own VM instead of putting it on my Ubuntu services VM. I figured it would be easier to manage, troubleshoot, and back up separately.

## Proxmox VM

VM specs:

* 4 vCPU
* 8 GB RAM
* 80 GB disk
* Ubuntu Server

<img width="831" height="542" alt="image" src="https://github.com/user-attachments/assets/06ef7880-8c78-4ac4-9770-ec017aa965b4" />

## Ubuntu Server Installation

Installed Ubuntu Server on the new `wazuh01` VM.

<img width="1443" height="899" alt="image" src="https://github.com/user-attachments/assets/7f5678ce-509f-4208-b8d0-6624d6710988" />

### Network

<img width="1444" height="893" alt="image" src="https://github.com/user-attachments/assets/0f3c297a-6902-4c35-8e1d-048e058f6767" />

Network settings:

```text
Interface: ens18
Network: 192.168.8.0/24
IP Assignment: DHCP
Network Device: VirtIO
```

I am using DHCP for now. I may switch this VM to a static IP later since Wazuh agents need to consistently reach the server.

## Storage

<img width="1429" height="897" alt="image" src="https://github.com/user-attachments/assets/352e7d5a-2b39-4dc0-9ff2-fbea304f1fa3" />

I gave the VM an 80 GB virtual disk.

<img width="1448" height="896" alt="image" src="https://github.com/user-attachments/assets/bbcf0128-d7f3-4026-96f1-ca6262895e16" />

Ubuntu was installed using LVM. Around 70 GB was given to the root filesystem and I left some free space in the volume group in case I need to expand it later.

## SSH

<img width="1445" height="897" alt="image" src="https://github.com/user-attachments/assets/8e3adb56-d63e-4897-874e-6c3b2832a2aa" />

Enabled OpenSSH Server during installation so I can manage the VM remotely instead of always using the Proxmox console.

## Optional Packages

<img width="1436" height="897" alt="image" src="https://github.com/user-attachments/assets/a0637793-4a45-42cd-8fdc-8ff51ced7377" />

Skipped the optional Ubuntu snaps since I wanted to keep the VM pretty minimal and only install what I actually need.

# Wazuh Installation

Installed the Wazuh components on the Ubuntu VM:

* Wazuh Manager
* Wazuh Indexer
* Wazuh Dashboard

After the installation finished, I checked the services and was able to log into the Wazuh dashboard.

<img width="1064" height="49" alt="image" src="https://github.com/user-attachments/assets/9c28af0b-91fb-4862-ae0d-76883cabbef9" />

At this point the main Wazuh server is running.

# Adding Agents

Next step is adding some of my other homelab systems as agents.

I plan on starting with:

* Windows Server 2022
* Ubuntu services VM
* Possibly my Windows desktop later

<img width="611" height="263" alt="image" src="https://github.com/user-attachments/assets/8e91a69b-0fa7-4296-8735-fe09badc6531" />

The main goal is to make sure the agents are checking in and actually sending logs to Wazuh.

# Things I Want to Test

## File Integrity Monitoring

I want to test Wazuh's File Integrity Monitoring by watching a folder and then creating, editing, and deleting files to see what alerts are generated.

## Windows Event Logs

Once my Windows Server is added, I want to monitor Windows security events and login activity.

## Failed Login Detection

I also want to purposely cause some failed Windows and Linux logins and see how Wazuh detects them.

## Vulnerability Detection

I want to use Wazuh to check my VMs for vulnerable packages/software and then patch some of them to see if the findings disappear.

## MITRE ATT&CK

I also want to look through the alerts and see which ones Wazuh maps to MITRE ATT&CK techniques.

## Custom Rules

After I understand the default rules better, I want to try making a few custom rules of my own.

Some ideas:

* Multiple failed logins
* SSH login failures
* Changes to important files
* Admin account activity

# Troubleshooting

I ran into a few issues during the setup.

One of the main problems was getting a permission denied error while working with the Wazuh installation files.

After checking the VM and rebooting it, I was able to continue the setup and eventually got all of the main Wazuh services running.

I want to keep adding problems I run into here along with what fixed them instead of only showing the successful parts of the setup.

# Current Progress

* [x] Created dedicated Wazuh VM
* [x] Installed Ubuntu Server
* [x] Enabled SSH
* [x] Installed Wazuh
* [x] Logged into Wazuh dashboard
* [ ] Add Windows Server agent
* [ ] Add Ubuntu agent
* [ ] Verify events are coming in
* [ ] Test File Integrity Monitoring
* [ ] Test failed logins
* [ ] Check vulnerability detection
* [ ] Review MITRE ATT&CK alerts
* [ ] Create custom rules
* [ ] Add dashboard and alert screenshots

# Goal

The main goal of this project is to get more comfortable with how a SIEM actually works instead of just reading about one.

I want to be able to generate activity on one of my systems, see that activity show up in Wazuh, understand why it triggered an alert, and figure out what I would do about it.
