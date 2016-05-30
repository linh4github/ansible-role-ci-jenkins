# Ansible Role - Jenkins CI Server

[![Build Status](https://travis-ci.org/elnebuloso/ansible-role-ci-jenkins.svg?branch=master)](https://travis-ci.org/elnebuloso/ansible-role-ci-jenkins)

Jenkins CI Server for Linux Server.

## Requirements

This role requires Ansible 2.0 or higher, and platform requirements are listed in the metadata file.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```
ci_jenkins_hostname: "jenkins.box.entwickl.de"

# mounting jenkins workspace
ci_jenkins_mount_src: "nas.fritz.box:/jenkins"
ci_jenkins_mount_type: "nfs"

# mounting jenkins thin-backup plugin directory
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

- `apache2` should be installed and working (you can use the `elnebuloso.apache2` role to install).

##  License

MIT

##  Author Information

This role was created in 2016 by [elnebuloso](https://github.com/elnebuloso/)