# PAN-OS Configurations using Ansible Playbooks
This repository contains Ansible playbooks that automates the configurational and operational tasks on Palo Alto Network Next-Gen Firewalls, using the PAN-OS API.
Playbooks are written for firewalls as well as Panorama.

## Requirements
Following requirements were fulfilled before creating and testing playbooks,
- Red Hat Enterprise Linux Server
- Python
- Ansible
- PAN-OS Ansible Collection

## Tested Operating System
Red Hat Enterprise Linux Server release 7.9 (Maipo)

## Tested Ansible Version
This collection of playbooks is tested with the most current Ansible releases.  
All playbooks are executed and tested on Ansible version 2.13.5.

## Tested Python Version
The minimum python version for this collection is Python 3.8.  
All playbooks are executed and tested on Python 3.8.12.

## Tested PAN-OS Versions
All playbooks are executed and tested on PAN-OS 10.1.6 and 10.2.3.

## Support
This Collection of Ansible Playbooks is created using the help of [published Ansible Galaxy](https://galaxy.ansible.com/paloaltonetworks/panos), and it is to be freely used under an as-is, best effort, support
policy. These scripts should be seen as community supported. 

## Pre-Requisites
PAN-OS Ansible Collection should be installed from Ansible Galaxy, and following files should be configured prior executing the playbooks (except for API Key Retrievals),
- [Ansible Configuration File](ansible.cfg)
- [Hosts File](hosts)
- [Variables](group_vars/panos_devices/vars)
- [Vault](group_vars/panos_devices/vault)

Following is the directory structure maintained during the test cases,
```bash
.
├── ansible.cfg
├── ansible-logfile
├── group_vars
│   └── panos_devices
│       ├── vars
│       └── vault
└── hosts
```


## Use Cases
Following playbooks are created and tested,

### API Key Retrieval
Below playbooks will allow retrieval of the api_key for a given username/password against Panorama/Firewall
- [API Key Retrieval using Curl](api-key-retrieval-curl.yml)
- [API Key Retrieval using PAN-OS API Module](api-key-retrieval-panos.yml)

more to be added soon ...

## Feedback & Questions
Have a suggestion? Open an Enhancement request. Pull requests are also welcome.  
Contribute your configurational and operational tasks for PAN-OS.
