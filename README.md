# MongoDB
Manage MongoDB databases.

## Requirements
[supported platforms](https://github.com/r-pufky/ansible_mongodb/blob/main/meta/main.yml)

## Role Variables
[defaults](https://github.com/r-pufky/ansible_mongodb/tree/main/defaults/main)

### Ports
All ports and protocols have been defined for the role.

[defaults/ports.yml](https://github.com/r-pufky/ansible_mongodb/blob/main/defaults/main/ports.yml)

## Dependencies
**galaxy-ng** roles cannot be used independently. Part of
[r_pufky.srv](https://github.com/r-pufky/ansible_collection_srv) collection.

## Example Playbook
Read defaults documentation. Enterprise licensing not supported at this time.

Deploy a default Debian configuration using MongoDB repositories.
``` yaml
- name: 'mongodb server'
  hosts: 'mongodb.example.com'
  become: true
  roles:
     - 'r_pufky.srv.mongodb'
```


Alternative setup enabling weekly backups, using custom storage locations.
``` yaml
- name: 'mongodb server'
  hosts: 'mongodb.example.com'
  become: true
  roles:
     - 'r_pufky.srv.mongodb'
  vars:
    mongodb_srv_backup_enable: true
    mongodb_srv_backup_dir: '/data/mongodb/backup'
    mongodb_srv_backup_schedule: 'weekly'
    mongodb_cfg_storage_db_path: '/data/mongodb/mongod'
    mongodb_cfg_storage_data_path: '/data/mongodb/mongot'
```

### Deploying versions with different configuration settings.
Apply role for each specific instance. MongoDB releases outside of the role
releases version may have limited support.

See documentation.

Please submit a bug if a new version of MongoDB has been released and updated
default configuration variables are needed.

## Development
Configure [environment](https://github.com/r-pufky/ansible_collection_docs/blob/main/ansible/environment.md)

Run all unit tests:
``` bash
molecule test --all
```

### Releases
Release format: **{OS}-{SERVICE}-{ROLE}**

Each type inherits the versioning system used; defaulting to schematic
versioning.

`12.0.0-2.0.3-1.0.0`

* 12.0.0 - Debian 12 (bookworm).
* 2.0.3 - Service/app version.
* 1.0.0 - Role version.

Releases are branched on Debian releases:

* **[13.x.x](https://github.com/r-pufky/ansible_mongodb)**: 13 Trixie.
* **[12.x.x](https://github.com/r-pufky/ansible_mongodb/tree/12.x)**: 12 Bookworm.

## Issues
Create a bug and provide as much information as possible.

Associate pull requests with a submitted bug.

## License
[AGPL-3.0 License](https://www.tldrlegal.com/license/gnu-affero-general-public-license-v3-agpl-3-0)
 [(direct link)](https://github.com/r-pufky/ansible_mongodb/blob/main/LICENSE)

## Author Information
PGP Fingerprint: [466EEC2B67516C7117C85CE3A0BC35D16698BAB9](https://keys.openpgp.org/vks/v1/by-fingerprint/466EEC2B67516C7117C85CE3A0BC35D16698BAB9)
| [github gist](https://gist.github.com/r-pufky/a8df36977c55b5bb20829267c4c49d22)
