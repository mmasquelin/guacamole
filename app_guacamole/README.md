Apache Guacamole
================

Modular Ansible Role for deploying and configuring Apache Guacamole server on GNU/Linux Debian Buster.

Requirements
------------

* GNU/Linux Debian 10 (buster)

Role Variables
--------------

Available variables are listed below with their default values (you can also see defaults/main.yml).

| Variable                 | Description                                         |
| ------------------------ | --------------------------------------------------- |
| guacamole_version        | guacd version number to install - default: `1.2.0`  |
| guacamole_src_dir        | Installation repository - default:  `/usr/local/src`|
| guacamole_conf_dir       | guacd config directory - defaut: `/etc/guacamole`   |
| guacamole_dl_url         | Installation source URL                             |  
| guacamole_server_package | Filename to download from source URL                |  
| guacamole_user           | Unix user/group details - default: `guacd`          |
| guacamole_admin_user     | Admin username - default: `sysad`                   |
| guacamole_admin_pass     | Admin password - default: `guacadmin`               |

Dependencies
------------

None.

Example Playbook
----------------

```yaml
---
- name: Playbook to deploy Apache Guacamole
  hosts: debian
  vars:
    - guacamole_ldap_auth: false
    - guacamole_postgresql_backend: false
  roles:
    - role: geerlingguy.postgresql
      when: guacamole_postgresql_backend|bool
    - role: app_guacamole
```

License
-------

GPLv2

Author Information
------------------

* [Mickaël MASQUELIN](mailto:mickael.masquelin@univ-lille.fr)
* [https://www.linkedin.com/mmasquelin](https://www.linkedin.com/mmasquelin)