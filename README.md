ageres210784.ansible_walg
=========

Role for wal-g installation and configuration.

Requirements
------------

Ansible Galaxy

Role Variables
--------------

You can see all vars in `default/main.yml` vars file.

To restore by a certain time you should use the following variables:

- postgresql_conf_recovery - configeration for postgresql (for more information see <https://postgrespro.ru/docs/postgresql/12/runtime-config-wal?lang=en#RUNTIME-CONFIG-WAL-RECOVERY-TARGET>)
- walg_restore_name - name of the backup (for more information see <https://github.com/wal-g/wal-g/blob/master/docs/PostgreSQL.md#backup-fetch>)

```yaml
postgresql_conf_recovery:
  - recovery_target_action='promote'
  - recovery_target_time='2021-07-15 11:35:04'
  - recovery_target_timeline='current'
walg_restore_name: base_0000000300000000000000DA
walg_restore: yes
```

Dependencies
------------

None

Tested with Ansible
-------------------

    2.9

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: ageres210784.ansible_walg
```

License
-------

Apache 2.0

Author Information
------------------

Evseev Sergey
