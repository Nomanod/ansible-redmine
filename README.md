Role Name
=========

Install or Upgrade redmine

Requirements
------------

To Install:
- ANXS.mysql

Role Variables
--------------


You must set the databases variable

---
db_host: "127.0.0.1"
db_name: "redmine"
db_username: "admin"
db_password: "unaContrasenia"



redmine_domain: "name.domain"
redmine_files: "{{ redmine_path }}/files"
redmine_lang: "es"
redmine_path: "/opt/redmine"
redmine_proxy: "/etc/nginx/conf.d/redmine_proxy"
redmine_public: "{{ redmine_path }}/public"
redmine_version: "2.5.2"

target_dump: "/opt/redmine.sql.bz2"
target_files: "/opt/redmine.tar.bz2"

ssl_cert: "/etc/ssl/local/server.crt"
ssl_key: "/etc/ssl/local/server.key"


update: false
nginx: false


A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

- ANXS.mysql

mysql_port: 3306
mysql_bind_addres: "0.0.0.0"
mysql_root_password: "dificil"
mysql_databases:
 - name: "{{ db_name }}"
mysql_users:
 - name: "{{ db_username }}"
   pass: "{{ db_password }}"
   priv: "{{ db_name }}.*:ALL"


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

GPLv3
