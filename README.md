ajgarlag.rollback
=================

Ansible role to rollback applications heavily inspired by [ansistrano](https://github.com/ansistrano/rollback).

Role Variables
--------------

* **ajgarlag_rollback_path**: Path where the code has been deployed to (defaults to `{{ansible_env.HOME}}/project`).

### Role hooks

You can hook your own tasks files to the rollback process defining any of the following vars:

* **ajgarlag_rollback_before_setup_tasks_file**
* **ajgarlag_rollback_after_setup_tasks_file**
* **ajgarlag_rollback_before_symlink_tasks_file**
* **ajgarlag_rollback_after_symlink_tasks_file**
* **ajgarlag_rollback_before_cleanup_tasks_file**
* **ajgarlag_rollback_after_cleanup_tasks_file**

To do it, you must define the desired var with the path to the tasks file:

```yml
ajgarlag_rollback_after_symlink_tasks_file: "{{ playbook_dir }}/tasks/after_symlink.yml"
```

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
