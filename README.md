Role Name
=========

Installs ECO:Global Survial stand-alone game server.

https://www.strangeloopgames.com/eco/

Requirements
------------

Systemd based linux distribution with apt packaging.

Note the version of mono supplied with Ubuntu 16.04 is insufficent to run the server.  This role will install the ubuntu mono repo.  Set `mono_repo: false` if your distribution already has the compatible packages or you need them from somewhere else.

Role Variables
--------------

Variable | Description | Default
--- | --- | ---
version | Version to install. | 0.7.2.5-beta
install_path | Base directory to install the server | /opt/eco
service_name | Name of systemd service (use for multiple daemons) | eco-server
mono_repo | Install the official mono apt repository for ubuntu | true

See `defaults/main.yml`

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: foonix.eco-server, version: 0.7.2.5-beta }

License
-------

BSD

Author Information
------------------

https://github.com/foonix
