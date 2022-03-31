# Ansible Collection - kencx.ansible

## Roles
- `security` provides basic hardening such as configuring `sudo`, SSH hardening,
  installing ufw and fail2ban
- `terraform` installs Terraform CLI

## Playbooks
Bootstraps a brand new development workstation. Tested on Ubuntu 21.04.

Refer to `playbooks` for more details.

## Molecule
To debug roles, run:

```bash
$ molecule converge -s security
$ molecule verify -s security
```

When running roles with `service`, systemd is required. However,
[there](https://github.com/geerlingguy/docker-ubuntu2004-ansible/issues/18) are
[issues](https://github.com/ansible-community/molecule/discussions/3108) with
running systemd in Docker containers.

Additionally, `apt update` is not working in Debian 10 container due to
"oldstable".

## Development
When testing locally, the collection can be quickly installed to the
collections' path with

```bash
$ ansible-galaxy install -f -r requirements.yml
```

## TODO
