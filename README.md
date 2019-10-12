# Ansible Role s3fs

Library of Ansible plugins and roles for deploying various services.
See [ansible-roles](https://github.com/davidfischer-ch/ansible-roles) for additional documentation.

This repository hosts the role s3fs and may depend of other roles and plugins of the library.

## Dependencies

See [meta](meta/main.yml).

## Variables

TODO VARIABLES

## Example

### PlayBook

```
---

- hosts:
    - all:!localhost
  roles:
    - s3fs
    - mounts
```

### Variables

```
mounts:
  data:
    check: yes
    directory: /mnt/mybucket
    user: root
    group: root
    mode: 777
    fstype: fuse.s3fs
    options: _netdev,allow_other,noatime,endpoint=eu-west-1,iam_role=auto,max_stat_cache_size=60000,storage_class=standard_ia,use_sse
    source: mybucketname:/some/path

s3fs_version: v1.82  # 20/09/2018
```

## License

See [LICENSE.rst](LICENSE.rst).

## Authors

See [AUTHORS](AUTHORS).

2014-2019 - David Fischer
