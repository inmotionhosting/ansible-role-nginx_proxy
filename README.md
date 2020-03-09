inmotion.nginx-proxy
=========

Modular Ansible Role for deploying and configuring Nginx as a reverse-proxy

[![Build Status](https://travis-ci.org/inmotionhosting/inmotion.nginx-proxy.png?branch=master)](https://travis-ci.org/inmotionhosting/inmotion.nginx-proxy)

Requirements
------------

* CentOS 7.x or later
* Debian 8 or later
* Ubuntu 16.04 LTS or later

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: www
      roles:
         - role: inmotion.nginx-proxy

License
-------

GPLv3

Author Information
------------------

InMotion Hosting
