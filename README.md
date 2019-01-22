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

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

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

License
-------

MIT

