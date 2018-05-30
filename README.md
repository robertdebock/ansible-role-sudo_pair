sudo-pair
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-sudo-pair.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-sudo-pair)

Provides sudo-pair for your system.

Context
-------
This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/robertdebock.github.io/artifacts/sudo-pair.png "Dependency")

Requirements
------------

Access to a repository containing packages, likely on the internet.

Role Variables
--------------

- sudo_pair_version:
- sudo-pair_gids_enforced: 0
- sudo-pair_gids_exempted: none

Dependencies
------------

This role can be used to prepare your system:

- robertdebock.bootstrap
- robertdebock.epel
- robertdebock.buildtools

Download the dependencies by issuing this command:
```
ansible-galaxy install --role-file requirements.yml
```

Compatibility
-------------

This role has been tested against the following distributions and Ansible version:

|distribution|ansible 2.3|ansible 2.4|ansible 2.5|
|------------|-----------|-----------|-----------|
|alpine-3.6|no|no|no|
|alpine-3.7|yes|yes|yes|
|archlinux|no|no|no|
|centos-6|no|no|no|
|centos-7|no|no|no|
|debian-buster|yes|yes|yes|
|debian-stretch|no|no|no|
|fedora-27|yes|yes|yes|
|fedora-28|yes|yes|yes|
|opensuse-42.2|no|no|no|
|opensuse-42.3|no|no|no|
|ubuntu-artful|yes|yes|yes|
|ubuntu-bionic|yes|yes|yes|

Example Playbook
----------------

The simplest way possible:
```
- hosts: servers

  roles:
    - robertdebock.bootstrap
    - robertdebock.buildtools
    - robertdebock.sudo-pair
```

Install this role using `galaxy install robertdebock.sudo-pair`.

License
-------

Apache License, Version 2.0

Author Information
------------------

Robert de Bock <robert@meinit.nl>
