[![Galaxy](https://github.com/roles-ansible/ansible_role_amdgpu_firmware/raw/main/.github/galaxy.svg)](https://galaxy.ansible.com/do1jlr/amdgpu_firmware)
[![License](https://github.com/roles-ansible/ansible_role_amdgpu_firmware/raw/main/.github/license.svg)](https://github.com/roles-ansible/ansible_role_amdgpu_firmware/blob/main/LICENSE)

 ansible role amdgpu_firmware
===============================

Ansible role to install some missing ``amdgpu`` Firmware for my AMD Leneovo Thinkpad *(``L14``)*.

This role is only running at:
```yaml
when:
```

+ It will download the defined Firmware Files from the ``rtl_nic__firmware`` variable.
+ Then we run ``update-initramfs -k all -u``.

You can change the downloaded firmware file names by modifying the default variables.

Optionally you can perform a simple versionscheck, that can prevent you from running a older version of this role accidentially.

 Variables
-----------
```yaml
---

# should we do a version check? (true is recomended)
submodules_versioncheck: false
```
