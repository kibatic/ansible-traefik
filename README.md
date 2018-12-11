kibatic.traefik
=========

Ansible role to deploy traefik binary and systemd unit.

[![Build Status](https://travis-ci.org/kibatic/ansible-traefik.svg?branch=master)](https://travis-ci.org/kibatic/ansible-traefik)

Træfɪk is a modern HTTP reverse proxy and load balancer made to deploy microservices with ease. It supports several backends (Docker, Swarm, Kubernetes, Marathon, Mesos, Consul, Etcd, Zookeeper, BoltDB, Rest API, file…) to manage its configuration automatically and dynamically.

Installation
--------------

`$ ansible-galaxy install kibatic.traefik`

Role Variables
--------------

```yml
traefik_install_dir: /usr/bin
traefik_binary_url: https://github.com/containous/traefik/releases/download/v1.7.5/traefik_linux-amd64
traefik_bin_path: "{{ traefik_install_dir }}/traefik"
traefik_config_file: /etc/traefik.toml
traefik_template: traefik.toml
traefik_systemd_unit_template: traefik.service
traefik_systemd_unit_dest: /etc/systemd/system/traefik.service
```


Configuration
----------------

Create a custom config file `templates/traefik.toml.j2`.
Override template variable (e.g. in `group_vars/all.yml` )

```yml
traefik_template: templates/traefik.toml
```

Add role to your playbook.

```yml
    - hosts: servers
      roles:
         - { role: kibatic.traefik, tags: traefik }
```

Update Traefik
--------------

You have to change `traefik_binary_url` or update this role. Then run your playbook
with following **extra vars** :

```bash
$ ansible-playbook playbook.yml -t traefik --extra-vars "traefik_update=yes"
```

Use same command if you want to downgrade.

License
-------

MIT
