# Ansible Collection - haught.apcos

This collection allows for the network configuration of APC UPS v3 NMCs running v1.4.2.1 or greater.

All APC NMCv2 and NMCv3 with version less than v1.4.2.1 are not supported due to a weird command line echoing buffering that makes Ansible fail. APC was kind enough to fix this bug for us in the v1.4.2.1 release for the v3 cards.

## Current Modules

[haught.apcos.apcos_command](plugins/modules/network/apcos/apcos_command.py) - A module to run CLI commands against APC NMCs.

[haught.apcos.apcos_dns](plugins/modules/network/apcos/apcos_dns.py) - A module to configure DNS on APC NMCs.

[haught.apcos.apcos_ntp](plugins/modules/network/apcos/apcos_ntp.py) - A module to configure NTP on APC NMCs.

[haught.apcos.apcos_radius](plugins/modules/network/apcos/apcos_radius.py) - A module to configure RADIUS on APC NMCs.

[haught.apcos.apcos_snmp](plugins/modules/network/apcos/apcos_snmp.py) - A module to configure SNMP v2c on APC NMCs.

[haught.apcos.apcos_snmpv3](plugins/modules/network/apcos/apcos_snmpv3.py) - A module to configure SNMP v3 on APC NMCs.

[haught.apcos.apcos_system](plugins/modules/network/apcos/apcos_system.py) - A module to configure system option on APC NMCs.

# Developing

Create the directory hierarchy *ansible_collections/haught/apcos* and clone the repo directly into *apcos*

Symlink the *apcos* directory to your default ansible collection directory with the haught subdirectory. For example:
```bash
mkdir ~/.ansible/collections/ansible_collections/haught
ln -s ~/devel/ansible_collections/haught/apcos ~/.ansible/collections/ansible_collections/haught/
```


Sanity tests of all modules:
```bash
ansible-test sanity --docker --python 3.6
```

Unit tests of all modules:
```bash
ansible-test units --docker --python 3.6
```

(You can add a specific module name to the end of the command to the test just that module)