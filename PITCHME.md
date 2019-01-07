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

@size[30px](Ansible is open source software that automates software provisioning, configuration management, and application deployment.)

@ol[](false)
- Configurations stored in YAML (dot yml)
- Uses pre-configured WinRM to communicate with Windows
- Runs on a control linux system (or WSL)
@olend

---

### Modules

@size[18px](Index of modules can be found at:)
@size[20px]([https://docs.ansible.com/ansible/latest/modules/list_of_windows_modules.html](https://docs.ansible.com/ansible/latest/modules/list_of_windows_modules.html))

![mods](assets/image/mods.jpg)

---

@size[25px](win_user - Manages local Windows user accounts)

```plaintext
> ansible windows_servers `
    -m win_user `
    -a "name=vagrant state=absent"

ansi-node-01.ad.piccola.us | SUCCESS => {
    "changed": true,
    "msg": "User 'vagrant' deleted successfully",
    "name": "vagrant",
    "state": "absent"
}
```
@[1]
@[2]
@[3]
@[5-9]
---

### Inventory

@size[25px](Defaults to `/etc/ansible/hosts` and may be represented as either INI or YAML. Can be overridden with `-i ./acme_inventory`.)

```ini
dockerlin.piccola.us

[windows]
ansi-node-01.ad.piccola.us
ansi-node-02.ad.piccola.us

[web]
ansi-node-02.ad.piccola.us
```
---