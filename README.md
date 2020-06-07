# AWX-RPM Ansible Installer
This Ansible installer is a "translation" (almost) line-by-line of the awx-setup python installer at https://raw.githubusercontent.com/MrMEEE/awx-rpm/master/awx-setup

The installer must only be used for an installation from scratch; it does not include the Update option.

TODO: 
- add Red Hat repositories
- include an "upgrade" option
- make versionlock idempotent in CentOS 8

The Vagrantfile included allows installing AWX-RPM on both CentOS 7 and CentOS 8 Virtual Machines

This installer can be used to perform the AWX-RPM installation on any system given a proper ansible "inventory" file.

# Start and provision both instances, centos7 and centos8
````
vagrant up

````
Warning: this will start both VMs. This will eat up lots of RAM. 

# Start one instance but don't provision it
````
vagrant up centos7 --no-provision

````

# Start instance, make clean snapshot and provision
````
vagrant up centos7 --no-provision
vagrant snapshot save centos7 clean
vagrant centos7 provision

````
# Restore snapshot and provision again
````
vagrant snapshot restore centos7 clean
vagrant centos7 provision

````
# Ansible Vagrant Guide
https://docs.ansible.com/ansible/latest/scenario_guides/guide_vagrant.html

## Running Ansible Manually
https://docs.ansible.com/ansible/latest/scenario_guides/guide_vagrant.html#running-ansible-manually

ansible-playbook -i .vagrant/provisioners/ansible/inventory/vagrant_ansible_inventory playbook.yml


