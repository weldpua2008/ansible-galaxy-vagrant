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
      gather_facts: true
      roles:
        - weldpua2008.vagrant
        
      vars:
        vagrant_libvirt_enabled: true #In order to enable libvirt plugin          

If running on FreeBSD use variable  `freebsd_install_from_ports`:
* True - use ports
* False - use pkg_add / pkgng - Package manager for FreeBSD >= 9.

    - name: Setup for vagrant boxes
      hosts: all
      gather_facts: true
      vars:        
        freebsd_install_from_ports: True
      roles:
        - weldpua2008.vagrant
      

# License

MIT License

# Author

Valeriy Solovyov 
