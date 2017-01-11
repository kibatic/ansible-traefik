Role Name
=========

A brief description of the role goes here.

Role Variables
--------------

```yml
traefik_install_dir: /usr/local/bin
traefik_binary_url: https://github.com/containous/traefik/releases/download/v1.1.2/traefik_linux-amd64
traefik_bin_path: "{{ traefik_install_dir }}/traefik"
traefik_config_dir: /etc/traefik
```


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: kibatic.traefik }

License
-------

MIT
