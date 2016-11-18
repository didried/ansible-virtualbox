# ansible role: virtualbox

[![Build Status](https://travis-ci.org/didried/ansible-virtualbox.svg?branch=master)](https://travis-ci.org/didried/ansible-virtualbox)

An Ansible role for installing VirtualBox on Ubuntu.

## Requirements

This role requires Ansible 2.0 or higher.

Tested on Ubuntu 12.04 and 14.04. Should work on all Ubuntu versions >= 12.04.

## Role Variables

Default variables:

``` yaml
---
# defaults file for virtualbox
virtualbox_version: "5.0"
virtualbox_install_dkms: no
```

## Dependencies

None.

## Example Playbook

Use the option '--ask-become-pass' (or alias '-K') when running playbook using this role with ansible-playbook (like 'ansible-playbook -i ./hosts vbox.yml -K').

Install VirtualBox:
``` yaml
- hosts: all
  roles:
    - { role: didried.virtualbox }
```

Install specific version of VirtualBox and virtualbox-dkms:
``` yaml
- hosts: all
  roles:
    - { role: didried.virtualbox, virtualbox_version: "4.2", virtualbox_install_dkms: yes }
```

## Installation

### Installation from Github directly

To install from GitHub directly add the source to requirements.yml:
``` yaml
- name: didried.virtualbox
  src: https://github.com/didried/ansible-virtualbox
```

And add the command to your playbook:
``` yaml
- name: install requirements from ansible galaxy
  command: ansible-galaxy install -r requirements.yml --ignore-errors
```
This playbook has to be run before using the role in another playbook.

## License

MIT

## Author Information

Daniel Hubmann
