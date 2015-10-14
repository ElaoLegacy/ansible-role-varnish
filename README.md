WARNING: This role is no longer maintained !!!
==============================================

You are strongly encouraged to switch to the new roles stack on https://github.com/ElaoInfra
--------------------------------------------------------------------------------------------

By the way, this role will remain available on https://github.com/ElaoLegacy
----------------------------------------------------------------------------


Ansible Role - Varnish
======================

A role to install and configure varnish

Requirements
------------

Debian / Ubuntu

Configuration example:
---------------------

```
elao_varnish:
    start:                  "yes"
    nfiles:                 131072
    memlock:                82000
    instance:               "My hostname"
    vcl:                    "/etc/varnish/default.vcl"
    address:                "127.0.0.1"
    port:                   80
    admin_listen_address:   "127.0.0.1"
    admin_listen_port:      6082
    min_threads:            1
    max_threads:            1000
    thread_timeout:         120
    storage_type:           "malloc"    # Could be malloc, file
    storage_file:           "/var/lib/varnish/$INSTANCE/varnish_storage.bin"
    storage_size:           "1G"
    secret_file:            "/etc/varnish/secret"
    default_ttl:            120
```

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: elao.varnish }

License
-------

MIT

Author Information
------------------

http://www.elao.com/