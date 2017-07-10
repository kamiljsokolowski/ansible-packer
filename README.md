# README.md
# Ansible role: Packer 1.x.x

[![Build Status](https://travis-ci.org/kamiljsokolowski/ansible-role-packer.png)](https://travis-ci.org/kamiljsokolowski/ansible-role-packer)

Ansible role that installs [Packer](https://www.packer.io/) 1.x.x on Linux-based platforms.

## Requirements
If you are using SSL/TLS, you will need to provide your own certificate and key files. You can generate a self-signed certificate with a command like `openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout example.key -out example.crt`.

## Supported platforms
- Ubuntu: 14.04+
- *RedHat/CentOS (comming soon)*

## Role variables
Available variables are listed below, along with default values:

| Variable | Required | Default | Comments |
|----------|----------|---------|----------|
| `packer_archive_download_url_prefix` | No | `https://releases.hashicorp.com/packer` | Prefix for Packer archive download URL. |
| `packer_archive_version` | No | `1.0.2` | Packer archive version. |
| `packer_archive_sha256` | No | `13774108d10e26b1b26cc5a0a28e26c934b4e2c66bc3e6c33ea04c2f248aad7f` | Checksum for checking Packer archive integrity. |
| `packer_install_directory` | No | `/usr/local/bin` | Directory, where Packer binary will be installed. |

## Dependencies
*(Null)*

## Example playbook
Install Packer on the host server using default options:
```
- name: Ansible Packer role with default options.
  hosts: all
  gather_facts: true
  roles:
    - ansible-packer
```
Install custom Packer version on the host server to user' local binaries directory:
```
- name: Ansible Packer role with default options
  hosts: all
  gather_facts: true
  roles:
    - ansible-packer
      packer_archive_version: 1.0.0
      packer_install_directory: ~/bin/
```

## License
MIT

## Authors
Kamil Sokolowski (<kamil.sokolowski@finastra.com>)
