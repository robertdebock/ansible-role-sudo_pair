# [sudo-pair](#sudo-pair)

Install and configure sudo-pair on your system.

|Travis|GitHub|GitLab|Quality|Downloads|Version|
|------|------|------|-------|---------|-------|
|[![travis](https://travis-ci.com/robertdebock/ansible-role-sudo-pair.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-sudo-pair)|[![github](https://github.com/robertdebock/ansible-role-sudo-pair/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-sudo-pair/actions)|[![gitlab](https://gitlab.com/robertdebock/ansible-role-sudo-pair/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-sudo-pair)|[![quality](https://img.shields.io/ansible/quality/)](https://galaxy.ansible.com/robertdebock/sudo-pair)|[![downloads](https://img.shields.io/ansible/role/d/)](https://galaxy.ansible.com/robertdebock/sudo-pair)|[![Version](https://img.shields.io/github/release/robertdebock/ansible-role-sudo-pair.svg)](https://github.com/robertdebock/ansible-role-sudo-pair/releases/)|

## [Example Playbook](#example-playbook)

This example is taken from `molecule/resources/converge.yml` and is tested on each push, pull request and release.
```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: robertdebock.sudo-pair
      sudo_pair_gids_exempted:
        - 123
      sudo_pair_gids_enforced:
        - 321
```

The machine needs to be prepared in CI this is done using `molecule/resources/prepare.yml`:
```yaml
---
- name: Prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: robertdebock.bootstrap
    - role: robertdebock.core_dependencies
    - role: robertdebock.buildtools
    - role: robertdebock.cargo
    - role: robertdebock.git
```

Also see a [full explanation and example](https://robertdebock.nl/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

These variables are set in `defaults/main.yml`:
```yaml
---
# defaults file for sudo-pair

# The version to install.
sudo_pair_version: sudo_pair-v1.0.0

# The userids that are exempted
# sudo_pair_gids_exempted:
#   - 123

# The userids that are enforced
# sudo_pair_gids_enforced:
#   - 321
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/robertdebock/ansible-role-sudo-pair/blob/master/requirements.txt).

## [Status of requirements](#status-of-requirements)

The following roles are used to prepare a system. You may choose to prepare your system in another way, I have tested these roles as well.

| Requirement | Travis | GitHub |
|-------------|--------|--------|
| [robertdebock.bootstrap](https://galaxy.ansible.com/robertdebock/bootstrap) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-bootstrap.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-bootstrap) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-bootstrap/actions) |
| [robertdebock.buildtools](https://galaxy.ansible.com/robertdebock/buildtools) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-buildtools.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-buildtools) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-buildtools/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-buildtools/actions) |
| [robertdebock.cargo](https://galaxy.ansible.com/robertdebock/cargo) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-cargo.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-cargo) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-cargo/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-cargo/actions) |
| [robertdebock.core_dependencies](https://galaxy.ansible.com/robertdebock/core_dependencies) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-core_dependencies.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-core_dependencies) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-core_dependencies/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-core_dependencies/actions) |
| [robertdebock.epel](https://galaxy.ansible.com/robertdebock/epel) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-epel.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-epel) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-epel/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-epel/actions) |
| [robertdebock.git](https://galaxy.ansible.com/robertdebock/git) | [![Build Status Travis](https://travis-ci.com/robertdebock/ansible-role-git.svg?branch=master)](https://travis-ci.com/robertdebock/ansible-role-git) | [![Build Status GitHub](https://github.com/robertdebock/ansible-role-git/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-git/actions) |

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://robertdebock.nl/) for further information.

Here is an overview of related roles:
![dependencies](https://raw.githubusercontent.com/robertdebock/drawings/artifacts/sudo-pair.png "Dependency")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/robertdebock):

|container|tags|
|---------|----|
|amazon|all|
|el|7, 8|
|debian|buster, bullseye|
|fedora|all|
|opensuse|all|
|ubuntu|focal, bionic, xenial|

The minimum version of Ansible required is 2.9, tests have been done to:

- The previous version.
- The current version.
- The development version.

## [Exceptions](#exceptions)

Some variarations of the build matrix do not work. These are the variations and reasons why the build won't work:

| variation                 | reason                 |
|---------------------------|------------------------|
| Alpine | cannot produce cdylib for `sudo_pair v0.11.1 (/tmp/sudo_pair-sudo_pair-v0.11.1/sudo_pair)` as the target `x86_64-unknown-linux-musl` does not support these crate types |

## [Included version(s)](#included-versions)

This role [refers to a version](https://github.com/robertdebock/ansible-role-sudo-pair/blob/master/defaults/main.yml) released by square on GitHub. Check the released version(s) here:
- [sudo_pair](https://github.com/square/sudo_pair/releases).

This version reference means a role may get outdated. Monthly tests occur to see if [bit-rot](https://en.wikipedia.org/wiki/Software_rot) occured. If you however find a problem, please create an issue, I'll get on it as soon as possible.
## [Testing](#testing)

[Unit tests](https://travis-ci.com/robertdebock/ansible-role-sudo-pair) are done on every commit, pull request, release and periodically.

If you find issues, please register them in [GitHub](https://github.com/robertdebock/ansible-role-sudo-pair/issues)

Testing is done using [Tox](https://tox.readthedocs.io/en/latest/) and [Molecule](https://github.com/ansible/molecule):

[Tox](https://tox.readthedocs.io/en/latest/) tests multiple ansible versions.
[Molecule](https://github.com/ansible/molecule) tests multiple distributions.

To test using the defaults (any installed ansible version, namespace: `robertdebock`, image: `fedora`, tag: `latest`):

```
molecule test

# Or select a specific image:
image=ubuntu molecule test
# Or select a specific image and a specific tag:
image="debian" tag="stable" tox
```

Or you can test multiple versions of Ansible, and select images:
Tox allows multiple versions of Ansible to be tested. To run the default (namespace: `robertdebock`, image: `fedora`, tag: `latest`) tests:

```
tox

# To run CentOS (namespace: `robertdebock`, tag: `latest`)
image="centos" tox
# Or customize more:
image="debian" tag="stable" tox
```

## [License](#license)

Apache-2.0


## [Author Information](#author-information)

[Robert de Bock](https://robertdebock.nl/)

Please consider [sponsoring me](https://github.com/sponsors/robertdebock).
