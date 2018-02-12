Role Name
=========

**mysql_secure_installation** is Ansible role to improve MySQL installation
security. it do what **mysql_secure_installation** script do.

Requirements
------------

MariaDB/MySQL installation on the target machine.

Role Variables
--------------

```yml
---
# defaults file for ansible-role-mysql_secure_installation (msi)

# msi-mysql_root_pass >> if you already set the root password then assign it
# to this variable. by default there is no password.
msi-mysql_root_pass: ''

# msi-new_mysql_root_pass >> this will be the new mysql root password.
# if you don't want to change your old password then you can assign your old
# password to it too.
# oh and don't forget, always use ansible vault for sensitive data :)
#msi-new_mysql_root_pass
```

Example Playbook
----------------

```yml
---
- hosts: dbservers
  vars_files:
      - "{{ playbook_dir }}/sec_vars.yml" # ansible-vault secured variables file
  roles:
      - role: IBRAHIMMOHAMMAD.mysql_secure_installation
```

License
-------

BSD
