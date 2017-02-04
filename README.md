Role Name
=========

Ansible role for setting up guacamole server on ubuntu.

Requirements
------------

None.

Role Variables
--------------
Please pass in users and server dict. Example of it is shown below. 

  users:
    - { name: 'ichiban', pass: 'ichiV@gran7' }
    - { name: 'niban', pass: 'niV@gran7' }
    - { name: 'sanban', pass: 'sanV@gran7'}
    - { name: 'yonban', pass: 'yonV@gran7'}

  server_dict:
    - { server: "Active Directory", ip: "10.255.10.20" }
    - { server: "Storage Server", ip: "10.255.10.21" }
    - { server: "Terminal Server 1", ip: "10.255.10.22" }
    - { server: "Terminal Server 2", ip: "10.255.10.23" }

Below are the default vars that could be changed. 

guacd_port: 4822
window_port: 3389
tomcat: tomcat7
guac_home: /usr/share/{{ tomcat }}/.guacamole
guac_server: 0.9.9
guac_client: 0.9.9

Dependencies
------------

None.

Example Playbook
----------------

---
  - hosts: all
    gather_facts: true
    become: true
    roles:
      - guac_setup

License
-------

MIT

Author Information
------------------

chaosmuskey@gmail.com
