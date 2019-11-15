# NetApp Ansible Playbooks

#### Date: 3-8-2019
#### Version: 1


## Description

Contained within this repository are NetApp Ansible playbooks

## File Listing & Description
1. combined/00_netapp_full_install.yml<br>
 
   
   It will setup a NetApp cluster ready for VMware vSphere NFS datastores. It performs the following:
```sh
    - Set NTP
    - Set Timezone
    - Rename the Root Aggregate
    - Create and online a new Data Aggregate
    - Create a Vserver
    - Setup a VLAN
    - Creating a Broadcast Domain
    - Subnet Creation
    - Creating an NFS Lif
    - Start NFS
    - Create NFS Export Rule
    - Add DNS Settings to Vserver
    - Create first NFS Volume
    - Create an additional NFS Volume
 ```
 
   Be sure to change the variables within the yml file to match your environment
 
   To run this ansible playbook simply execute: ansible-playbook 00_netapp_full_install.yml
 
 2. multi-part/netapp_full_install_multi-part.yml<br>
    multi-part/variables.yml<br>
    multi-part/01_install_licenses_setup_ntp.yml<br>
    multi-part/02_create_aggregate.yml<br>
    multi-part/03_create_svm.yml<br>
    multi-part/04_network_setup.yml<br>
    multi-part/05_create_volume.yml<br>
    multi-part/06_mount_nfs_datastore.yml<br>

    This plabook is part of my second Ansible/NetApp/VMware blog post:<br>
    https://www.sysadmintutorials.com/creating-multi-part-ansible-playbook-with-variables-netapp-vmware/<br>
    
    These runbooks are an improvement on the one gigantic runbook created in step 1. above.
    Please head on over to the blog post to read what has changed.
    
    To run this ansible playbook simply execute: ansible-playbook netapp_full_install_multi-part.yml
