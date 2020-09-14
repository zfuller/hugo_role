# Role Name

Installs [Hugo](https://gohugo.io/) framework from hugos [github](https://github.com/gohugoio/hugo)s [release page](https://github.com/gohugoio/hugo/releases)

## Requirements

There are no requirements to run hugo, though you will need a webserver (apache2/nginx/caddy/etc) to view your hugo website.

## Role Variables
set this variable to true to upgrade an existing installation
```yaml
hugo_force_install: false
```
you can set this to a specific release version,
or have this role automatically grab the latest version
```yaml
hugo_version:
```

Example:
```yaml
hugo_version: 0.74.3
```

If you are running on `ARM` or `ARM64`, you'll want to set this variable as such, otherwise ansible will detect only 32bit or 64bit
```yaml
hugo_bit:
```

Install hugo extended
```yaml
hugo_extended: true
```

Change default bin path
```yaml
hugo_bin_path: /usr/local/bin
```


## Dependencies

N/A

## Example Playbook

```yaml
---
- name: Hugo Install
  hosts: hugo
  become_method: sudo
  become: yes
  gather_facts: yes
  roles:
    - zfuller.hugo_role
```

## License

GPL-3.0-only

## Author Information

zfuller
