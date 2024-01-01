# nrpe

[![quality](https://img.shields.io/ansible/quality/27910)](https://galaxy.ansible.com/vbotka/nrpe)[![Build Status](https://travis-ci.org/vbotka/ansible-nrpe.svg?branch=master)](https://travis-ci.org/vbotka/ansible-nrpe)

[Ansible role.](https://galaxy.ansible.com/vbotka/nrpe/) Install and configure NRPE.

Nagios Remote Plugin Executor (NRPE)

Feel free to [share your feedback and report issues](https://github.com/vbotka/ansible-nrpe/issues).

[Contributions are welcome](https://github.com/firstcontributions/first-contributions).


## Requirements

### Roles

- [vbotka.ansible_lib](https://galaxy.ansible.com/vbotka/ansible_lib)

### Collections

- community.general


## Variables

Review defaults and examples in vars.


## Workflow

1) Install roles

```bash
shell> ansible-galaxy role install vbotka.nrpe
shell> ansible-galaxy role install vbotka.ansible_lib
```

1) Install the collection if necessary

```bash
shell> ansible-galaxy collection install community.general
```

2) Change variables, for example in vars/main.yml

```bash
shell> editor vbotka.nrpe/vars/main.yml
```

3) Create playbook and inventory

```yaml
shell> cat nrpe.yml
- hosts: webserver
  roles:
    - vbotka.nrpe
```

```ini
shell> cat hosts
[webserver]
<webserver-ip-or-fqdn>
[webserver:vars]
ansible_connection=ssh
ansible_user=freebsd
ansible_become=true
ansible_become_method=sudo
ansible_python_interpreter=/usr/local/bin/python3.9
ansible_perl_interpreter=/usr/local/bin/perl
```

4a) Check syntax

```bash
shell> ansible-playbook nrpe.yml --syntax-check
```

4b) Display variables

```bash
shell> ansible-playbook nrpe.yml -e nrpe_debug=true -t nrpe_debug
```

4c) Install packages

```bash
shell> ansible-playbook nrpe.yml -e nrpe_install=true -t nrpe_packages
```

4d) Create /usr/local/etc/nrpe.cfg

```bash
shell> ansible-playbook nrpe.yml -t nrpe_conf_create
```

4e) Dry-run and show changes

```bash
shell> ansible-playbook nrpe.yml --check --diff
```

5) Run the playbook if all seems to be right

```bash
shell> ansible-playbook nrpe.yml
```

6) Plugins (TBD)
		

## References

- [NRPE Manual pdf](http://nagios.sourceforge.net/docs/nrpe/NRPE.pdf)
- [NRPE - Nagios Core Addons](https://assets.nagios.com/downloads/nagioscore/docs/nagioscore/4/en/addons.html#nrpe)
- [How To Install NRPE - FreeBSD](https://support.nagios.com/kb/article.php?id=515#FreeBSD)


## License

[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)


## Author Information

[Vladimir Botka](https://botka.info)
