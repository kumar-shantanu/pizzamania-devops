Nagios NRPE Server Config
=========
An Ansible role to handle the installation and rollout of the Nagios NRPE Daemon.

Currently supports:

 * Debian
   - Squeeze
   - Wheezy
 * Ubuntu
   - Raring
   - Saucy
   - Trusty
 * RedHat
   - At least 6 onwards

Requirements
------------

None

Role Information
--------------

This role gives you the ability to deploy plugins on a global and per-server basis. 

Role Variables
--------------

  * *nagios_nrpe_server_bind_address*: 127.0.0.1
  * *nagios_nrpe_server_port*: 5666
  * *nagios_nrpe_server_allowed_hosts*: 127.0.0.1

These are OS specific and likely wont want to be changed

Debian:

  * *nagios_nrpe_server_pid*: /var/run/nagios/nrpe.pid
  * *nagios_nrpe_server_user*: nagios
  * *nagios_nrpe_server_group*: nagios
  * *nagios_nrpe_server_service*: nagios-nrpe-server
  * *nagios_nrpe_server_plugins_dir*: /usr/lib/nagios/plugins
  * *nagios_nrpe_server_dir*: /etc/nagios

RedHat:

  * *nagios_nrpe_server_pid*: /var/run/nrpe/nrpe.pid
  * *nagios_nrpe_server_user*: nrpe
  * *nagios_nrpe_server_group*: nrpe
  * *nagios_nrpe_server_repo_redhat*: epel
  * *nagios_nrpe_server_service*: nrpe
  * *nagios_nrpe_server_dir*: /etc/nagios

Dependencies
------------

N/A

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - nagio-nrpe
   vars:
     nagios_nrpe_server_allowed_hosts:
       - XXX.XXX.XXX.XXX
       - 127.0.0.1
```

License
-------

Apache

Author Information
------------------

Kumar Shantanu
