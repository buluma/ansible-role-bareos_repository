# Ansible role [bareos_repository](https://galaxy.ansible.com/ui/standalone/roles/buluma/bareos_repository/documentation)

Setup the [Bareos](https://www.bareos.com/) repositories.

|GitHub|Version|Issues|Pull Requests|Downloads|
|------|-------|------|-------------|---------|
|[![github](https://github.com/buluma/ansible-role-bareos_repository/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bareos_repository/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bareos_repository.svg)](https://github.com/buluma/ansible-role-bareos_repository/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-bareos_repository.svg)](https://github.com/buluma/ansible-role-bareos_repository/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-bareos_repository.svg)](https://github.com/buluma/ansible-role-bareos_repository/pulls/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/bareos_repository)](https://galaxy.ansible.com/ui/standalone/roles/buluma/bareos_repository/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-bareos_repository/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: yes
  gather_facts: yes

  roles:
    - role: buluma.bareos_repository
      bareos_repository_enable_tracebacks: yes
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-bareos_repository/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  become: yes
  gather_facts: no

  roles:
    - role: buluma.bootstrap
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-bareos_repository/blob/master/defaults/main.yml):

```yaml
---
# defaults file for bareos_repository

# What type of Bareos to install, either "community" or "subscription".
bareos_repository_type: community

# The subscription username for the repository.
bareos_repository_username: ""

# The subscription password for the repository.
bareos_repository_password: ""

# What release to use, either "current", "next" or "release".
# When using `bareos_repository_type: community` this can be set to "release" or "testing".
bareos_repository_release: current

# The version of Bareos to install.
# Only affects `bareos_repository_type: subscription`.
bareos_repository_version: 23

# You can enable tracebacks for troubleshooting purposes.
bareos_repository_enable_tracebacks: false
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-bareos_repository/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.bareos_repository](https://galaxy.ansible.com/buluma/bareos_repository)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bareos_repository/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bareos_repository/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bareos_repository.svg)](https://github.com/shadowwalker/ansible-role-bareos_repository)|
|[buluma.buildtools](https://galaxy.ansible.com/buluma/buildtools)|[![Ansible Molecule](https://github.com/buluma/ansible-role-buildtools/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-buildtools/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-buildtools.svg)](https://github.com/shadowwalker/ansible-role-buildtools)|
|[buluma.epel](https://galaxy.ansible.com/buluma/epel)|[![Ansible Molecule](https://github.com/buluma/ansible-role-epel/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-epel/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-epel.svg)](https://github.com/shadowwalker/ansible-role-epel)|
|[buluma.python_pip](https://galaxy.ansible.com/buluma/python_pip)|[![Ansible Molecule](https://github.com/buluma/ansible-role-python_pip/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-python_pip/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-python_pip.svg)](https://github.com/shadowwalker/ansible-role-python_pip)|
|[buluma.postgres](https://galaxy.ansible.com/buluma/postgres)|[![Ansible Molecule](https://github.com/buluma/ansible-role-postgres/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-postgres/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-postgres.svg)](https://github.com/shadowwalker/ansible-role-postgres)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-bareos_repository/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[Debian](https://hub.docker.com/r/buluma/debian)|bookworm, bullseye, buster|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|7, 8, 9|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|38, 39|
|[opensuse](https://hub.docker.com/r/buluma/opensuse)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|jammy|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-bareos_repository/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-bareos_repository/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-bareos_repository/blob/master/LICENSE)

## [Author Information](#author-information)

[Shadow Walker](https://buluma.github.io/)
