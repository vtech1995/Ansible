Role Name: apache
=========

Example role for installing, configuring, and starting Apache
web server with a virtual host.

Requirements
------------

Ansible 2.9 or later.
Target node must be running either a Red Hat based distribution
(e.g. RHEL, CentOS, Fedora) or a Debian based distribution
(e.g. Debian, Ubuntu).

Role Variables
--------------

vhost_user:
     The name of the user account that should own the vhost's
     document directory contents. Defaults to "user1".

vhost_group:
     The name of the group that should own the vhost's document
     directory contents. Defaults to "users".

vhosts_root_directory:
     The path to the directory where the vhost's document
     directory tree will be created. Note that role will create
     a subdirectory there matching the target host's hostname,
     and will make that the vhost's document root directory.
     Defaults to "/var/www/vhosts".

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: web_servers
      become: True
      roles:
         - role: apache
           vars:
             - vhost_user: user

License
-------

N/A

Author Information
------------------

NetApp Lab on Demand
