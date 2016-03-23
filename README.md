Role Name
=========

A simple Role to create an upstart service


Requirements
------------

Role Variables
--------------
* `upstart_name`: name of the service
* `upstart_description`: description of the service
* `upstart_chdir`: directory where the command should be executed in
* `upstart_command`: command to start
* `upstart_user`: user to run as
* `upstart_group`: group to run as
* `upstart_env`: list with environemnt variables to set
* `upstart_log_directory`: directory of logfile
* `upstart_log_filename`: logfile
* `upstart_pidfile_directory`: directory for pidfile
* `upstart_pidfile_filename`: pidfile


Example Playbook
----------------

    - hosts: servers
      roles:
        - role: basserselim.upstart
          upstart_name: node-app
          upstart_description: "service for node-app"
          upstart_command: "node app.js"
          upstart_chdir: "/var/www/node-app"
          upstart_user: www-data
          upstart_group: www-data
          upstart_env:
            NODE_ENV: "production"
          upstart_log_directory: "/var/log/node-app"
          upstart_log_filename: "output.log"
          upstart_pidfile_directory: "/var/run/node-app"
          upstart_pidfile_filename: "node-app.pid"

License
-------

BSD

Author Information
------------------

