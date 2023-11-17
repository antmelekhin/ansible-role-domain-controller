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

- `domain_controller_dns_domain_name` The DNS name of the domain which should exist and be reachable or reside on the target Windows host (default: `''`).
- `domain_controller_domain_netbios_name` The NetBIOS name for the root domain in the new forest (default: `''`).
- `domain_controller_safe_mode_password` Safe mode password for the domain controller (default: `''`).
- `domain_controller_domain_mode` Specifies the domain functional level of the first domain in the creation of a new forest (default: `WinThreshold`).
- `domain_controller_forest_mode` Specifies the forest functional level for the new forest (default: `WinThreshold`).
- `domain_controller_dns_delegation` Whether to create a DNS delegation that references the new DNS server that you install along with the domain controller (default: `false`).
- `domain_controller_install_dns` Whether to install the DNS service when creating the domain controller (default: `true`).
- `domain_controller_database_path` The path to a directory on a fixed disk of the Windows host where the domain database will be created (default: `C:\Windows\NTDS`).
- `domain_controller_log_path` Specifies the fully qualified, non-UNC path to a directory on a fixed disk of the local computer where the log file for this operation is written (default: `C:\Windows\NTDS`).
- `domain_controller_sysvol_path` The path to a directory on a fixed disk of the Windows host where the Sysvol file will be created (default: `C:\Windows\SYSVOL`).

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
