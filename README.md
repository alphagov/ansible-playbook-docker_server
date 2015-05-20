Docker_server
=========

An ansible role to install a docker node.

Requirements
------------

Only tested on Ubuntu 14.04.

Role Variables
--------------

`docker_port` port that docker listens on.

Dependencies
------------

* None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: docker-nodes
      roles:
         - { role: docker_server, docker_port: 4567 }

License
-------

See `LICENSE` file.
