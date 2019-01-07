## @color[#2e75e8](PowerShell) + @color[#C51A00](Ansible)
### Playbooks, DSC, Roles and more

---

### Agenda

- Introduction
- Ad-hoc modules
- Playbooks
- Desired State Configuration (DSC)
- Roles

---

### Ansible

#### Ansible is open source software that automates software provisioning, configuration management, and application deployment.

@ol[](false)
- Configurations stored in YAML (dot yml)
- Uses pre-configured WinRM to communicate with Windows
- Runs on a control linux system (or WSL)
@olend

---

### Modules

@size[18px](Index of modules can be found at)

@size[20px]([https://docs.ansible.com/ansible/latest/modules/list_of_windows_modules.html](https://docs.ansible.com/ansible/latest/modules/list_of_windows_modules.html))


![mods](assets/image/mods.jpg)

---

### win_user - Manages local Windows user accounts

```
> ansible windows_servers -l ansi-node-01.ad.piccola.us -m win_user -a "name=vagrant state=present password=2c0mplex!"
ansi-node-01.ad.piccola.us | SUCCESS => {
    "account_disabled": false,
    "account_locked": false,
    "changed": true,
    "description": "",
    "fullname": "vagrant",
    "groups": [],
    "name": "vagrant",
    "password_expired": false,
    "password_never_expires": false,
    "path": "WinNT://AD/ANSI-NODE-01/vagrant",
    "sid": "S-1-5-21-1999347826-3707782961-4063531653-1005",
    "state": "present",
    "user_cannot_change_password": false
}
```