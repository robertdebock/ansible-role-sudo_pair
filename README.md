sudo-pair
=========

[![Build Status](https://travis-ci.org/robertdebock/ansible-role-sudo-pair.svg?branch=master)](https://travis-ci.org/robertdebock/ansible-role-sudo-pair)

The purpose of this role is to install and configure sudo-pair on your system.

Example Playbook
----------------

This example is taken from `molecule/default/playbook.yml`:
```
---
- name: Converge
  hosts: all
  become: true
  gather_facts: false

  roles:
    - robertdebock.bootstrap
    - robertdebock.buildtools
    - robertdebock.cargo
    - robertdebock.sudo-pair

```

Role Variables
--------------

These variables are set in `defaults/main.yml`:
```
---
# defaults file for sudo-pair

# The version to install.
sudo_pair_version: sudo_pair-v0.11.1

# The userids that are exempted
# sudo_pair_gids_exempted: 123

# The userids that are enforced
# sudo_pair_gids_enforced: 123

# To update all packages installed by this roles, set `sudo-pair_package_state` to `latest`.
sudo-pair_package_state: present

```

Requirements
------------

- Access to a repository containing packages, likely on the internet.
- A recent version of Ansible. (Tests run on the last 3 release of Ansible.)

The following roles can be installed to ensure all requirements are met, using `ansible-galaxy install -r requirements.yml`:

---
- robertdebock.bootstrap
- robertdebock.epel
- robertdebock.buildtools
- robertdebock.cargo


Context
-------

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/drawings/artifacts/sudo-pair.png "Dependency")


Compatibility
-------------

This role has been tested against the following distributions and Ansible version:

|distribution|ansible 2.4|ansible 2.5|ansible 2.6|ansible 2.7|ansible devel|
|------------|-----------|-----------|-----------|-----------|-------------|
|alpine-edge*|no|no|no|no|no*|
|alpine-latest|no|no|no|no|no*|
|archlinux|yes|yes|yes|yes|yes*|
|centos-6|no|no|no|no|no*|
|centos-latest|yes|yes|yes|yes|yes*|
|debian-latest|yes|yes|yes|yes|yes*|
|debian-stable|yes|yes|yes|yes|yes*|
|debian-unstable*|yes|yes|yes|yes|yes*|
|fedora-latest|yes|yes|yes|yes|yes*|
|fedora-rawhide*|yes|yes|yes|yes|yes*|
|opensuse-leap|yes|yes|yes|yes|yes*|
|opensuse-tumbleweed|yes|yes|yes|yes|yes*|
|ubuntu-artful|yes|yes|yes|yes|yes*|
|ubuntu-devel*|yes|yes|yes|yes|yes*|
|ubuntu-latest|yes|yes|yes|yes|yes*|

A single star means the build may fail, it's marked as an experimental build.

Testing
-------

[Unit tests](https://travis-ci.org/robertdebock/ansible-role-sudo-pair) are done on every commit and periodically.

If you find issues, please register them in [GitHub](https://github.com/robertdebock/ansible-role-sudo-pair/issues)

To test this role locally please use [Molecule](https://github.com/metacloud/molecule):
```
pip install molecule
molecule test
```
There are many specific scenarios available, please have a look in the `molecule/` directory.


License
-------

Apache-2.0


Author Information
------------------

[Robert de Bock](https://robertdebock.nl/) <robert@meinit.nl>
