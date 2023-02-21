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


## Using Flags For Better Visibility
We can take usage of multiple flags while executing a playbook, few of them are mentioned below,
- --check
  - This flag (check mode) when used, will only check the syntax. It is just a dry run or a simulation. It will not generate output for tasks that use conditionals based on registered variables (results of prior tasks). However, it is great for validating configuration management playbooks that run on one node at a time
  - ```bash
    ansible-playbook some-playbook.yml --check
    ```  
- --diff
  - This flag when used with playbook execution, will display the differences which are made during the execution. When this flag is supplied and the module supports this, Ansible will report back the changes made. This is mostly used in modules that manipulate files (i.e. template) but other modules might also show ‘before and after’ information
  - ```bash
    ansible-playbook some-playbook.yml --diff
    ```  
- --diff and --check
  - The --diff option to ansible-playbook works great with --check (detailed above). When using both flags while executing a playbook, ansible will simulate and dry run the playbook and will show the changes that would have been made
  - ```bash
    ansible-playbook some-playbook.yml --diff --check
    ```  


## Use Cases
Following playbooks are created and tested,

### API Key Retrieval
Below playbooks will allow retrieval of the api_key for a given username/password against Panorama/Firewall
- [API Key Retrieval using Curl](api-key-retrieval-curl.yml)
- [API Key Retrieval using PAN-OS API Module](api-key-retrieval-panos.yml)

### Create, Update and Delete Address Object
Below playbook includes multiple tasks, creating address-object (having different types), updating existing address-object and deleting an address-object
- [Address Object Tasks](address-object.yml)

### Create, Update and Delete Address Object Group
By using below playbooks, we can manipulate the entries in our address object groups
- [Create Address Object Group](address-object-group-create.yml)
- [Gather entries of existing Address Object Group](address-object-group-gather.yml)
- [Delete existing Address Object Group](address-object-group-delete.yml)
- [Add entries in existing Address Object Group](address-object-group-add-entries.yml)
- [Remove single entry from existing Address Object Group](address-object-group-remove-entry.yml)
- [Remove multiple entries from existing Address Object Group](addr-obj-grp-rmv-multiple-entries.yml)

more to be added soon ...

## Feedback & Questions
Have a suggestion? Open an Enhancement request. Pull requests are also welcome.  
Contribute your configurational and operational tasks for PAN-OS.
