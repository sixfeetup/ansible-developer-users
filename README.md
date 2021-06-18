ansible-developer-users
=========

User setup and SSH keys for SFUP developers.

Requirements
------------
-

Installation
------------
`requirements.yml`:
- src: git+ssh://git@github.com:sixfeetup/ansible-developer-users.git
  scm: git

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

additional_users: [] # see below
exclude: ["caleb"]
shell: /usr/bin/zsh
sudo_config: ALL=(ALL) NOPASSWD:ALL
optional_groups: ["zope", "docker"]

Dependencies
------------
-

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

- hosts: servers
  vars:
    additional_users:
      - name: bilbo
        fullname: Bilbo Baggins
        id: 140
        ssh_auth:
          - ssh-rsa seekret-tolkienabcdefghi bbb@thering.net
        state: present
        sudo_enabled: false

  tasks:
    - name: setup users
      import_role:
        name: ansible-developer-users

License
-------

MIT

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
