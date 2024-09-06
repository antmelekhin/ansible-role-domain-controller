Domain Controller
=================

An Ansible role for setup Active Directory domain controllers.

Requirements
------------

- Supported version of Ansible: 2.12 and highter.
- `pywinrm` is a python library for connection Ansible to Windows hosts via [WinRM](https://docs.ansible.com/ansible/latest/user_guide/windows_winrm.html).
- Supported platforms:
  - Windows
    - 2016
    - 2019

Role Variables
--------------

All variables that can be overridden are stored in the [defaults/main.yml](https://github.com/antmelekhin/ansible-role-domain-controller/blob/main/defaults/main.yml) file.
Please refer to the [meta/argument_specs.yml](https://github.com/antmelekhin/ansible-role-domain-controller/blob/main/meta/argument_specs.yml) file for a description of the available variables.

Dependencies
------------

None.

Example Playbook
----------------

```yaml
---

- name: Add Domain Controllers
  hosts: domain_controllers

  roles:
    - role: antmelekhin.domain_controller
      domain_controller_dns_domain_name: 'contoso.com'
      domain_controller_safe_mode_password: 'P@ssw0rd!'
```

License
-------

MIT

Author Information
------------------

Melekhin Anton.
