aadl.websocketd
=========

This role installs and configures a systemd service for it.

Requirements
------------

This role presumes a linux based server.

Use ansible >= 2.4.3 to get around issue (30753)[https://github.com/ansible/ansible/issues/30753]

Default Role Variables
--------------

```yaml
websocketd_install_path: '/usr/local/bin'

websocketd_user: 'www-data'
websocketd_group: 'www-data'

websocketd_service_options: []

websocketd_options: ''
```

Example Evergreen Variables
--------------

```yaml
websocketd_install_path: '/usr/local/bin'

websocketd_user: 'opensrf'
websocketd_group: 'opensrf'

websocketd_service_options:
  - 'Environment=PATH=/openils/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin'
  - 'Environment=LD_LIBRARY_PATH=/openils/lib:/usr/local/lib:/usr/local/lib/dbd:$LD_LIBRARY_PATH'

websocketd_options: '--loglevel error --maxforks 250 --port 7682 /openils/bin/osrf-websocket-stdio'
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables
passed in as parameters) is always nice for users too:

    - hosts: servers
      become: yes
      roles:
         - { role: aadl.websocketd }

License
-------

GPLv2
