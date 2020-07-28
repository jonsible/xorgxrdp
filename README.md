# jonsible.xorgxrdp

[![Build Status](https://travis-ci.com/jonsible/xorgxrdp.svg?branch=master)](https://travis-ci.com/jonsible/xorgxrdp)
[![Galaxy](https://img.shields.io/badge/galaxy-jonsible.xorgxrdp-blue.svg)](https://galaxy.ansible.com/jonsible/xorgxrdp/)

Role to install xorgxrdp

## Requirements

None.

## Role Variables

### Default usage

As default xorgxrdp is installed and running.
If you want to adapt this to your needs look at the [Advanced usage](#advanced-usage) section.

### Advanced usage

For more advanced usage the following variables are available:
```yaml
# See https://github.com/jonsible/builder for build variables
xorgxrdp:
  package: true                 # Install from repository (true/false)
  source:                       # If this hash is set, install from source
    version: &_version 0.2.12   # global version number
    contexts:                   # List of contexts
      - prefix: /usr/local      # Prefix to pass to ./configure
        owner: root             # Which user will own the software
        version: *_version      # context version. *_version references global version
```

A context is a combination of these three elements :
- A build prefix
- An owner
- A version (optional)

When installing from source, `xorgxrdp.source.version` will be used if no `contexts[].version` is set.

## Dependencies

None

## Example Playbook

Install xorgxrdp with the default settings
```yaml
- hosts: all
  roles:
     - role: jonsible.xorgxrdp
```

## License

GPL-3.0-or-later

## Author Information

This role was created in 2020 by [Jonathan Scherrer].
