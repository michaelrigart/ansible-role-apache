Ansible Apache Role
===================
[![Build Status](https://travis-ci.org/michaelrigart/ansible-role-apache.svg?branch=master)](https://travis-ci.org/michaelrigart/ansible-role-apache)

An Ansible role for installing and configuring Apache webserver

Role Variables
--------------

```yaml
apache_ppa_repo: define custom ppa to install apache from or leave blank
apache_packages: list of apache packages to install
apache_server_root: apache root path
apache_add_confs: list of configs to add. This will copy the conf from your files folder
apache_remove_confs: list of configs to remove
apache_enable_mods: list of modules to enable
apache_enable_confs: list of configs to enable
apache_add_sites:  list of sites to add. This will copy the vhosts from your files folder
apache_remove_sites: list of sites to remove
apache_enable_sites: list of sites to enable
apache2_service_state: indicates the service state; Allowed setting: started, stopped
apache2_service_enabled: indicates if service needs to be enabled on boot; Allowed settings: yes, no
```

Modules, configurations and sites will automatically be disabled when they are not present in the effective
apache_enable_* variable.

Example Playbook
-------------------------

```yaml
- hosts: servers
  roles:
     - { role: MichaelRigart.apache, sudo: Yes  }
```

License
-------

GPLv3

Author Information
------------------

Michaël Rigart <michael@netronix.be>
