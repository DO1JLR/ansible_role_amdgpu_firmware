[![Galaxy](https://github.com/roles-ansible/ansible_role_amdgpu_firmware/raw/main/.github/galaxy.svg)](https://galaxy.ansible.com/do1jlr/amdgpu_firmware)
[![License](https://github.com/roles-ansible/ansible_role_amdgpu_firmware/raw/main/.github/license.svg)](https://github.com/roles-ansible/ansible_role_amdgpu_firmware/blob/main/LICENSE)

 ansible role amdgpu_firmware
===============================

Ansible role to install some missing ``amdgpu`` Firmware for my AMD Leneovo Thinkpad *(``L14``)*.

This role is only running at:
```yaml
when:
  - ansible_processor[1] == 'AuthenticAMD'
```

+ It will download the defined Firmware Files from the ``amdgpu__firmware`` variable.
+ Then we run ``update-initramfs -k all -u``.

You can change the downloaded firmware file names by modifying the default variables.

Optionally you can perform a simple versionscheck, that can prevent you from running a older version of this role accidentially.

 Variables
-----------
```yaml
---
# define download url prefix
amdgpu__download_prefix: 'https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/plain'

# define firmware list
amdgpu__firmware:
  - 'amdgpu/vangogh_toc.bin'
  - 'amdgpu/vangogh_asd.bin'
  - 'amdgpu/navy_flounder_ta.bin'
  - 'amdgpu/navy_flounder_sos.bin'
  - 'amdgpu/vangogh_rlc.bin'
  - 'amdgpu/vangogh_mec2.bin'
  - 'amdgpu/vangogh_mec.bin'
  - 'amdgpu/vangogh_me.bin'
  - 'amdgpu/vangogh_pfp.bin'
  - 'amdgpu/vangogh_ce.bin'
  - 'amdgpu/navy_flounder_rlc.bin'
  - 'amdgpu/navy_flounder_mec2.bin'
  - 'amdgpu/navy_flounder_mec.bin'
  - 'amdgpu/navy_flounder_me.bin'
  - 'amdgpu/navy_flounder_pfp.bin'
  - 'amdgpu/navy_flounder_ce.bin'
  - 'amdgpu/vangogh_sdma.bin'
  - 'amdgpu/navy_flounder_sdma.bin'
  - 'amdgpu/vangogh_vcn.bin'
  - 'amdgpu/navy_flounder_vcn.bin'
  - 'amdgpu/arcturus_vcn.bin'
  - 'amdgpu/navy_flounder_smc.bin'
  - 'amdgpu/arcturus_smc.bin'
  - 'amdgpu/vangogh_dmcub.bin'
  - 'amdgpu/navy_flounder_dmcub.bin'

amdgpu__path_prefix: '/lib/firmware'
amdgpu__path_suffix: 'amdgpu'

# should we do a version check? (true is recomended)
submodules_versioncheck: false
```
