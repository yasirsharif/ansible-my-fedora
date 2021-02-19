Role Name
=========

A simple palybook to automatically configure my Fedora laptop.

Requirements
------------
After installing fedora, just install Ansible and git.
Clone this repository
`git clone https://github.com/yasirsharif/ansible-my-fedora.git`
Change the packages to be installed or the configs to suit your needs.
change to the directory where you cloned the repo and dry run:
`ansible-playbook tasks/main.yml --ask-become-pass --check`
if everything works fine, then run:
`ansible-playbook tasks/main.yml --ask-become-pass`

Done.
If Atom and Zoom installers throw an error:
*fatal: [localhost]: FAILED! => {"changed": false, "msg": "Failure downloading https://atom.io/download/rpm, Request failed: <urlopen error [Errno -3] Temporary failure in name resolution>", "results": []}*
Just re-run the playbook.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
