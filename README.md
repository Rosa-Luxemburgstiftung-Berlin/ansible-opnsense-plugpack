# ansible-opnsense-plugpack
ansible playbook for opnsens  that installs plugins and packages

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

`packages` are processed pefore `plugins`, `remove` is performed before `install`.
