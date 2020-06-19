# OpenWhisk Ansible role

![Basic role syntax check](https://github.com/nemonik/openwhisk-role/workflows/Basic%20role%20syntax%20check/badge.svg)

An Ansible role for ensuring the configuration of a [OpenWhisk](https://openwhisk.apache.org/).

## Requirements

Requires Kubernetes.

## Role Variables

| Variable                      | Required | Default               | Choices             | Comments                                         |
|-------------------------------|----------|-----------------------|---------------------|--------------------------------------------------|
| openwhisk_release_name        | yes      | owdev                 | String value        | The release name                                 |
| openwhisk_host                | yes      | not defined           | Private IP address  | IP address of OpenWhisk                          |
| openwhisk_insecureAPIHostPort | yes      | 80                    | Integer value       | Insecure API port                                |
| openwhish_apiHostPort         | yes      | 443                   | Integer value       | Secure API port                                  |
| images_cache_path             | no       | not defined           | Path                | Path to folder used to cache saved Docker images |

## Example Playbook

An example can be found used in my Hands-on DevOps course's [ansible/master-playbook.yml](https://github.com/nemonik/hands-on-DevOps/blob/master/ansible/master-playbook.yml).

```
- hosts: masters
  remote_user: vagrant
  roles:
    - common
    - k3s-server
    - openwhisk
```

The above Ansible playbook uses my [K3s-server role](https://github.com/nemonik/k3s-server-role) to install Lightweight Kubernetes (K3s).

For more information and to see this role put into action checkout my [Hands-on DevOps class](https://github.com/nemonik/hands-on-DevOps) project.

## License

3-Clause BSD License

## Author Information

Michael Joseph Walsh <mjwalsh@nemonik.com>
