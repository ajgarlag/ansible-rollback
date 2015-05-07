ajgarlag.rollback
=================

Ansible role to rollback applications heavily inspired by [ansistrano](https://github.com/ansistrano/rollback).

Role Variables
--------------

* **ajgarlag_rollback_path**: Path where the code has been deployed to (defaults to `{{ansible_env.HOME}}/project`).

Example Playbook
----------------

```yml
- hosts: all
  vars:
    ajgarlag_rollback_path: /var/www/application
  roles:
    - role: ajgarlag.rollback
```

License
-------

MIT

Author Information
------------------

Developed with ♥ by [Antonio J. García Lagar](http://aj.garcialagar.es).
