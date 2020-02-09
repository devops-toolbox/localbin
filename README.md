Role Name
=========

localbin: download, unpack and install various tools to /usr/local/bin or a defined
directory. Example: install pandoc.

[![Build Status](https://travis-ci.org/cmihai-ansible/localbin.svg?branch=master)](https://travis-ci.org/cmihai-ansible/localbin)

Ansible galaxy:
---------------

[https://galaxy.ansible.com/devopstoolbox.localbin](https://galaxy.ansible.com/devopstoolbox.localbin)

```bash
ansible-galaxy install devopstoolbox.localbin
```

Requirements
------------

- For RHEL, a Red Hat subscription or functional local repository.

Role Variables
--------------

See defaults for more examples. See vars to add more tools.
Will place binaries in `localbin_dir` or provided `dest`.
Will unpack .tar, .gz, .xz and .zip when setting `unpack: true`.

```yaml
localbin_user: root
localbin_dir: "/usr/local/bin"

localbin_micro_version: "1.4.1"
localbin_micro_checksum: "sha256:e7d4c9427f9fdfed78e69d42cf518e93ae15fc8f70b7f0f87d292ed81206e900
```

Dependencies
------------

- For Red Hat, subscription-manager.

Example Playbook
----------------

```yaml
---
- name: Install localbin on localhost
  hosts:
    - localhost
  connection: local

  tasks:
    - name: localbin is configured
      import_role:
        name: devopstoolbox.localbin
      vars:
        localbin_user: root
        localbin_dir: "/usr/local/bin"
        localbin_tools:
          localbin_user: root
          localbin_dir: "/usr/local/bin"

          localbin_micro_version: "1.4.1"
          localbin_micro_checksum: "sha256:e7d4c9427f9fdfed78e69d42cf518e93ae15fc8f70b7f0f87d292ed81206e900
      tags: localbin
```

License
-------

MIT

Author Information
------------------

- [Mihai Criveti](https://www.linkedin.com/in/devopstoolbox.)
