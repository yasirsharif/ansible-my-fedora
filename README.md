ansible-my-fedora
=========

A simple playbook to automatically configure my Fedora laptop.
This role is inspired by: https://gitlab.com/MikkCZ/ansible-fedora

Requirements
------------
After installing fedora, just install ansible and git:

`dnf install ansible git -y`

install ansible `community.general` collection:

`ansible-galaxy collection install community.general`

Clone this repository or install the role from Ansible Galaxy:

`git clone https://github.com/yasirsharif/ansible-my-fedora.git`

`ansible-galaxy install yasirsharif.ansible_my_fedora`

Customize the packages to be installed (in defaults/main.yml file) or the configuration (in tasks/desktop-config.yml file) to suit your needs.

Change to the directory where you cloned the repository `cd ansbile-my-fedora` and dry run:

`ansible-playbook test.yml --ask-become-pass --check`

if everything works fine, then run:

`ansible-playbook test.yml --ask-become-pass --tags update`

If you configured sudo without password:

`ansible-playbook test.yml --tags dev`

Done!

Role Variables
--------------

The variables: basic_packages, dev_tools, and sys_tools are defined in defaults/main.yml, you may add or remove packages to these lists as it suits your preferences.

Dependencies
------------
collections:
ansible `community.general` collection

Example Playbook
----------------

Below is part of the test.yml file
```
---
- hosts: localhost
  remote_user: user
  roles:
    - ansible-my-fedora
```

License
-------
GPL-3.0 License

Author Information
------------------
Yasir ElSharif

[@yasirsharif](https://twitter.com/yasirsharif)

https://www.linkedin.com/in/yasir-elsharif-8806a343/