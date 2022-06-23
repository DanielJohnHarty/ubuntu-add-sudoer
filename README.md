# ANSIBLE-ADD-UBUNTU-USER

Ensure that parameterised user exists on the remote.

- Creates the newuser group
- Creates the newuser and adds them to the newuser group
- Adds newuser to the sudo group [optional]
- Permits newuser passwordless sudo [optional]

### Variables

username: the newuser username to be created
user_comment: open text. Generally the full name.
sudoer: if yes, the user will given sudo privileges
passwordless_sudo: if yes, the user be allowed to sudo without password

### Playbook example example

```
- hosts: ubuntu_host
  become: yes
  vars:
    username: dharty
    user_comment: Daniel Harty
    sudoer: yes
    passwordless_sudo: yes
  tasks:
    - name: Add dharty user as passwordless sudoer
      import_role:
        name: ansible-add-ubuntu-sudoer
```
