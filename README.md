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
| cache_container_timeout       | no       | 300 seconds           | Integer value       | Number of seconds before Ansible times out       |              

## Example Playbook

An example can be found used in my Hands-on DevOps course's [ansible/master-playbook.yml](https://github.com/nemonik/hands-on-DevOps/blob/master/ansible/master-playbook.yml).

```
- hosts: masters
  remote_user: vagrant
  roles:
    - common
    - docker
    - k3s-server
    - metallb
    - openwhisk
```

The above Ansible playbook uses my

- [Common role](https://github.com/nemonik/common-role) to configure the instance past the base CentOS 7, Alpine 3.10 or Ubuntu Bionic image
- [Docker role](https://github.com/nemonik/docker-role) to install and configure Docker
- [K3s-server role](https://github.com/nemonik/k3s-server-role) to install Lightweight Kubernetes (K3s)
- [metallb role](https://github.com/nemonik/metallb-role) to install MetalLB
- [This role](https://github.com/nemonik/openwisk-role) to install Apache OpenWisk


For more information and to see this role put into action checkout my [Hands-on DevOps class](https://github.com/nemonik/hands-on-DevOps) project.

## License

3-Clause BSD License

## Author Information

Michael Joseph Walsh <mjwalsh@nemonik.com>
