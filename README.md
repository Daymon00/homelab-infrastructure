# Homelab Infrastructure

This repo documents my homelab and the different services, tools, and systems I’ve been setting up and learning with.
I mainly built this lab to get more hands on experience with system administration, networking, cybersecurity, virtualization, and automation.

## What I'm Running
* Proxmox VE
* Ubuntu Server
* Docker
* Windows Server/Active Directory
* Wazuh
* Pihole
* Portainer
* Jellyfin
* Sonarr/Radarr/Prowlarr
* RustDesk
* Tailscale for Rustdesk and other containers

## What I'm Using It For
Some of the main things I’m using the lab to learn and practice are:
* Managing virtual machines with Proxmox
* Windows Server and Active Directory
* Linux administration
* Docker and containerized services
* Network troubleshooting
* DNS filtering with Pihole
* Remote access to my server with Tailscale
* Security monitoring with Wazuh
* Backups and recovery
* Basic automation and scripting

## Setup
Most of my services run on Proxmox.
I have separate vms for windows server, linux services, and security tools. My ubuntu vm runs most of my Docker containers.
I’m also working on separating different parts of the network and learning more about vlans, firewall rules, and network security.

## Security
Some of the security related things I’m currently working with include:
* Wazuh SIEM
* Endpoint monitoring
* File integrity monitoring
* Vulnerability detection
* Active directory
* Pihole dns filtering
* Tailscale remote access
* Network segmentation
(I’ve also been testing alerts and different configurations so I can get more comfortable investigating security events instead of only installing the tools)

## Documentation
I’m using this repository to keep track of:
* Setup notes
* Configurations
* Network diagrams
* Docker compose files
* Scripts
* Troubleshooting notes
* Screenshots
* Things I learned along the way

## Things I Want to Add
Some things I plan on adding or learning next:
* Vlans
* Managed switch configuration
* Firewall configuration
* Grafana and Prometheus
* Ansible
* More wazuh testing
* Centralized logging
* More automation
* Better backups
* More network monitoring

This lab is still a work in progress and I’ll keep updating this repo as I add more things.
