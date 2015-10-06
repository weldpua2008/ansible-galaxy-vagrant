# WARNING: DEPRECATED

I don't use this anymore, and don't plan on maintaining it. Please use at your own risk.

# Ansible role for Vagrant

This role will configure your server with the standard default vagrant credentials.

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

Alexander Williams (Unscramble) - https://jidoteki.com
