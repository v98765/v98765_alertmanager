Role Name: Prometheus alertmanager
=========

Deploy and configure [alertmanager](https://github.com/prometheus/alertmanager)

Requirements
------------

Ansible 2.10

Role Variables
--------------

Name | Default Value
---|---
`alertmanager_version` | 0.23.0
`alertmanager_system_user` | "alertmanager"
`alertmanager_system_group` | "alertmanager"
`alertmanager_install_dir` | "/usr/local/bin"
`alertmanager_config_dir` | "/etc/alertmanager"
`alertmanager_db_dir` | "/var/lib/alertmanager"
`alertmanager_repo_dir` | "/var/tmp/archive"
`alertmanager_web_listen_address` | "0.0.0.0:9093"
`alertmanager_web_external_url` | "http://localhost:9093/"

check defaults/main.yml for config vars

```sh
mkdir -p /var/tmp/archive
cd /var/tmp/archive
wget https://github.com/prometheus/alertmanager/releases/download/v0.23.0/alertmanager-0.23.0.linux-amd64.tar.gz
```

Example Playbook
----------------

```yaml
---
- hosts: vmdb
  gather_facts: true
  connection: ssh
  roles:
    - v98765_alertmanager

```

copy templates to ./alertmanager/templates/

License
-------

BSD
