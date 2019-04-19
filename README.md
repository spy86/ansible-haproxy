Role Name
=========

Ansible Role install and configure haproxy.

Requirements
------------

 - CentOS 6/7
 - Debian 
 - Ubuntu 16.04

Role Variables
--------------

Configuration file is splited to 5 sections:

- haproxy_global : Process configuration
- haproxy_default : Generic configuration used by all other section)
- haproxy_frontends : where you define Input configuration
- haproxy_backends : where you can define list of backend server and manage them
- haproxy_admin : a small webinterface where you can monitor the haproxy status

More info about HAProxy configuration we can find in http://www.haproxy.org/download/2.0/doc/configuration.txt


Dependencies
------------

None

Example Playbook
----------------
```YAML
---
- hosts: servers
  remote_user: root
  roles:
   - role: ansible-haproxy
     haproxy_frontends:
     - name: loadbalancer
       bind: '*:8080'
       default_backend: webserver
     haproxy_backends:
     - name: webserver
       servers:
        - name: backend1
          ip: localhost
          port: 80
```
