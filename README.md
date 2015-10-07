[![Build Status](https://travis-ci.org/weldpua2008/ansible-galaxy-vagrant.svg?branch=master)](https://travis-ci.org/weldpua2008/ansible-galaxy-vagrant)
[![Ansible Role](https://img.shields.io/ansible/role/5398.svg?style=plastic)](https://galaxy.ansible.com/list#/roles/5398)

# Ansible role for Vagrant

This role will configure your server with vagrant. Also you can install extra providers:
* VirtualBox

# Usage example

Add this to your playbook:

    - name: Setup for vagrant boxes
      hosts: all
      gather_facts: true
      roles:
        - vagrant
        
      vars:
        vagrant_libvirt_enabled: true #In order to enable libvirt plugin          

If running on FreeBSD:

    - name: Setup for vagrant boxes
      hosts: all
      gather_facts: true
      vars:
        sudoers_path: /usr/local/etc/sudoers.d/vagrant
        vagrant_user_shell: /bin/sh
      roles:
        - vagrant

# License

MIT License

# Author

Valeriy Solovyov
