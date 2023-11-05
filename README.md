Ansible Role Template
=========

[![Molecule Test](https://github.com/diademiemi/ansible_role_vscode/actions/workflows/molecule.yml/badge.svg)](https://github.com/diademiemi/ansible_role_vscode/actions/workflows/molecule.yml)

This is an Ansible role to install and configure vscode.

Include more information about vscode in this section.

Requirements
------------
These platforms are supported:
- Ubuntu 20.04
- Ubuntu 22.04
- Debian 10
- Debian 11
- Debian 12
- EL 8 (Tested on Rocky Linux 8)
- EL 9 (Tested on Rocky Linux 9)
- Fedora 38
- openSUSE Leap 15.4

<!--
- List hardware requirements here  
-->

Role Variables
--------------

Variable | Default | Description
--- | --- | ---
`vscode_channel` | `stable` | Channel to install vscode from. Options: `["stable", "insiders"]`
`vscode_user` | `{{ ansible_user_id }}` | User to set up VSCode extensions and settings for
`vscode_extensions` | `[]` | List of VSCode extensions to install. See [defaults/main.yml](./defaults/main.yml) for examples.
`vscode_overwrite_settings` | `false` | Whether to overwrite existing VSCode settings
`vscode_settings` | `{}` | Dictionary of VSCode settings to set. See [defaults/main.yml](./defaults/main.yml) for examples.
<!--
`variable` | `default` | Variable example
`long_variable` | See [defaults/main.yml](./defaults/main.yml) | Variable referring to defaults
`distro_specific_variable` | See [vars/debian.yml](./vars/debian.yml) | Variable referring to distro-specific variables
-->

Dependencies
------------
<!-- List dependencies on other roles or criteria -->
None

Example Playbook
----------------

```yaml
- name: Use diademiemi.vscode role
  hosts: "{{ target | default('vscode') }}"
  roles:
    - role: "diademiemi.vscode"
      tags: ['diademiemi', 'vscode', 'setup']    ```

```

License
-------

MIT

Author Information
------------------

- diademiemi (@diademiemi)

Role Testing
------------

This repository comes with Molecule that run in Podman on the supported platforms.
Install Molecule by running

```bash
pip3 install -r requirements.txt
```

Run the tests with

```bash
molecule test
```

These tests are automatically ran by GitHub Actions on push. If the tests are successful, the role is automatically published to Ansible Galaxy.

