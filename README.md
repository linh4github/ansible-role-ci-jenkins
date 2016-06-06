# Ansible Role - Jenkins CI Server

[![Build Status](https://travis-ci.org/elnebuloso/ansible-role-ci-jenkins.svg?branch=master)](https://travis-ci.org/elnebuloso/ansible-role-ci-jenkins)

Jenkins CI Server for Linux Server.

## Requirements

This role requires Ansible 2.0 or higher, and platform requirements are listed in the metadata file.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```
ci_jenkins_proxy_port: "80"
ci_jenkins_proxy_hostname: "jenkins.box.entwickl.de"

# optional mounting jenkins workspace, leave empty for no mounting
ci_jenkins_mount_src: "nas.fritz.box:/jenkins"
ci_jenkins_mount_type: "nfs"

# optional mounting jenkins thin-backup directory, leave empty for no mounting
ci_jenkins_mount_backup_src: "nas.fritz.box:/jenkins-thin-backup"
ci_jenkins_mount_backup_type: "nfs"
```

## Example Playbook

```
- hosts: localhost
  vars:
    ci_jenkins_hostname: "jenkins.box.entwickl.de"
  roles:
    - { role: elnebuloso.ci-jenkins }
```

## Dependencies

None, but if Apache2 is installed, a proxy vhost will be configured.

##  License

MIT

##  Author Information

This role was created in 2016 by [elnebuloso](https://github.com/elnebuloso/)