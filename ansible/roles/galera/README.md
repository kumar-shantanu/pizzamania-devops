Role Name
========

ansible-galera -- build a galera cluser node

Requirements
------------

None

Role Variables
--------------

percona -- see main.yml in ./defaults

Dependencies
------------

None

License
-------

Apache 2.0

Author Information
------------------

Patrick "CaptTofu" Galbraith <patg@patg.net>

How do I use this?
------------------

Very simple. 

1. ansible-galaxy install --force --roles-path=/where/ever/you/want/your/roles CaptTofu.galera 

2. Add three galera hosts to your ansible hosts file

    [galera_cluster]
    host1
    host2
    host3

2. Use it in your playbook:


    - hosts: 
      - galera_cluster
    roles:
      - CaptTofu.ansible-galera

3. Run your playbook (this is for Docker)

    ansible-playbook -i hosts -u root cluster.yml

Other
------

See: 

