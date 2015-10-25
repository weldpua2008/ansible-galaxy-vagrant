[![Build Status](https://travis-ci.org/weldpua2008/ansible-galaxy-vagrant.svg?branch=master)](https://travis-ci.org/weldpua2008/ansible-galaxy-vagrant)
[![Ansible Role](https://img.shields.io/ansible/role/5398.svg?style=plastic)](https://galaxy.ansible.com/list#/roles/5398)
[![Project Stats](https://www.openhub.net/p/ansible-galaxy-vagrant/widgets/project_thin_badge.gif)](https://www.openhub.net/p/ansible-galaxy-vagrant/)


# Ansible role for Vagrant

This role will configure your server with vagrant. Also you can install extra providers:
* VirtualBox

# Usage example
    ansible-galaxy install weldpua2008.vagrant



Add this to your playbook:

    - name: Setup for vagrant boxes
      hosts: all
      sudo: yes
      gather_facts: true
      roles:
        - weldpua2008.vagrant
        
      vars:
        vagrant_libvirt_enabled: true #In order to enable libvirt plugin          

If running on FreeBSD use variable  freebsd_install_from_ports:
* True - use ports
* False - use pkg_add / pkgng - Package manager for FreeBSD >= 9

    - name: Setup for vagrant boxes
      hosts: all
      sudo: yes
      gather_facts: true
      vars:        
        freebsd_install_from_ports: True

      roles:
        - weldpua2008.vagrant
      

# Using SUDO with playbooks 
#### Become
http://docs.ansible.com/ansible/become.html#become
Before 1.9 Ansible mostly allowed the use of sudo and a limited use of su to allow a login/remote user to become a different user and execute tasks, create resources with the 2nd user’s permissions. As of 1.9 ‘become’ supersedes the old sudo/su, while still being backwards compatible. This new system also makes it easier to add other privilege escalation tools like pbrun (Powerbroker), pfexec and others.

#### sudo and su still work!
Old playbooks will not need to be changed, even though they are deprecated, sudo and su directives will continue to work though it is recommended to move to become as they may be retired at one point. You cannot mix directives on the same object though, Ansible will complain if you try to.

Become will default to using the old sudo/su configs and variables if they exist, but will override them if you specify any of the new ones.

# License

MIT License

# Author

Valeriy Solovyov 
