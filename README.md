ansible-my-fedora
=========

A simple playbook to automatically configure my Fedora laptop.
This role is inspired by: https://gitlab.com/MikkCZ/ansible-fedora

Requirements
------------
After installing fedora, just install ansible and git.
`dnf install ansible git -y`
Clone this repository
`git clone https://github.com/yasirsharif/ansible-my-fedora.git`
Change the packages to be installed (in defaults/main.yml file) or the configuration (in tasks/desktop-config.yml file) to suit your needs.
change to the directory where you cloned the repository `cd ansbile-my-fedora` and dry run:
`ansible-playbook tasks/main.yml --ask-become-pass --check`
if everything works fine, then run:
`ansible-playbook tasks/main.yml --ask-become-pass`

Done!

If Atom and Zoom installers throw an error:
*fatal: [localhost]: FAILED! => {"changed": false, "msg": "Failure downloading https://atom.io/download/rpm, Request failed: <urlopen error [Errno -3] Temporary failure in name resolution>", "results": []}*
Just re-run the playbook or disable them in default/main.yml file.

Role Variables
--------------

The variables: basic_packages, dev_tools, and sys_tools are defined in defaults/main.yml, you may add or remove packages to these lists as it suits your preferences.

Dependencies
------------
None as of my knowledge.

Example Playbook
----------------

Below is part of the main.yml file
```
---

- hosts: localhost
  connection: local
  vars_files:
    - ../defaults/main.yml
  tasks:
    - debug:
        msg: Setup my Fedora Laptop
    - name: Install required repositories
      include_tasks: repos.yml
    - name: Install basic packages
      include_tasks: packages.yml
    - name: Install Dev and Ops tools
      include_tasks: dev.yml
    - name: Install system tools
      include_tasks: sys-tools.yml
    - debug:
        msg: Configure my desktop, mouse and keyboard settings
    - name: Tweak my desktop
      include_tasks: desktop-config.yml
    - debug:
        msg: Uninstalling unwanted packages
    - name: remove unwanted apps
      include_tasks: uninstall.yml
```
License

-------
GPL-3.0 License

Author Information
------------------
Yasir ElSharif

[@yasirsharif](https://twitter.com/yasirsharif)

https://www.linkedin.com/in/yasir-elsharif-8806a343/
