[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](http://www.gnu.org/licenses/gpl-3.0)
[![lint](https://github.com/Rosa-Luxemburgstiftung-Berlin/ansible-opnsense-plugpack/actions/workflows/lint.yml/badge.svg)](https://github.com/Rosa-Luxemburgstiftung-Berlin/ansible-opnsense-plugpack/actions?query=workflow%3Aansible-lint)

# ansible-opnsense-plugpack
ansible playbook for opnsens that installs and removes plugins and packages.

## role variables

[defaults/main.yml](defaults/main.yml)

## caveats
do **not** list packages in `opn_packages` that are required/installed by **plugins** listed in `opn_plugins`!
(for example the package `lscpu` is installed by `os-hw-probe`)

## settings
```yaml
# define a list of opnsense plugins to install
opn_plugins:
  - os-lldpd
  - os-net-snmp

# opnsense plugins to remove
opn_plugins_remove:
  - os-dyndns

# list pf additional packages to install
opn_packages:
  - bash
  - bash-completion
  - bind-tools

# list of packages to remove
opn_packages_remove:
  - ipmitool

```

## order of processing
`plugins` are processed before `packages`, `remove` is performed before `install`.
