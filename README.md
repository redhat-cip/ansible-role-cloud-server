# Ansible Cloud: Server role

An Ansible role for managing virtual machines on the Cloud in an agnostic cloud provider way.

This role is part of the [ansible-cloud](https://github.com/redhat-cip/ansible-cloud) broader effort.

## Pre-requisites

Please refer to [ansible-cloud](https://github.com/redhat-cip/ansible-cloud) [README.md](https://github.com/redhat-cip/ansible-cloud/blob/master/README.md) to see how to configure your system the proper way for the provide you wish to use.


## Role Variables

| Variable name               | Required  | Default | Type   | Description                     |
|-----------------------------|-----------|---------|--------|---------------------------------|
| cloud_server_name           | True      | N/A     | String | Name of the VM                  |
| cloud_server_image          | True      | N/A     | String | Name of the image               |
| cloud_server_flavor         | True      | N/A     | String | Name of the flavor              |
| cloud_server_region         | True      | N/A     | String | Name of the region              |
| cloud_server_sshkey         | True      | N/A     | String | Name of the ssh keypair         |
| cloud_server_security_group | True      | N/A     | String | Name of the sec group to attach |


## Example

```
---
- hosts: localhost
  vars:
    ansible_cloud_provider: vultr
  tasks:
    - name: Create server
      include_role:
        name: cloud-server
      vars:
        cloud_server_name: ansiblecloud-testvm
        cloud_server_image: CentOS 7 x64
        cloud_server_flavor: 1024 MB RAM,25 GB SSD,1.00 TB BW
        cloud_server_region: Amsterdam
        cloud_server_sshkey: ansiblecloud-testsshkey
        cloud_server_security_group: ansiblecloud-testsecuritygroup
```


## License

Apache 2.0


## Authors Information

  - Ricardo Carrillo Cruz <ricarril@redhat.com>
  - Yanis Guenane <yguenane@redhat.com>
