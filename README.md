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

1) Install the role and collections

```
shell> ansible-galaxy role install vbotka.nrpe
shell> ansible-galaxy collection install community.general
```

2) Change variables, e.g. vars/main.yml

```
shell> editor vbotka.nrpe/vars/main.yml
```

3) Create playbook and inventory

```
shell> cat nrpe.yml
---
- hosts: webserver
  roles:
    - vbotka.nrpe
```

```
shell> cat hosts
[webserver]
<webserver-ip-or-fqdn>
[webserver:vars]
ansible_connection=ssh
ansible_user=freebsd
ansible_become=yes
ansible_become_method=sudo
ansible_python_interpreter=/usr/local/bin/python3.6
ansible_perl_interpreter=/usr/local/bin/perl
```

4a) Check syntax

```
shell> ansible-playbook nrpe.yml --syntax-check
```

4b) Display variables

```
shell> ansible-playbook nrpe.yml -e nrpe_debug=true -t nrpe-debug
```

4c) Install packages

```
shell> ansible-playbook nrpe.yml -e nrpe_install=true -t nrpe-packages
```

4d) Dry-run and show changes

```
shell> ansible-playbook nrpe.yml --check --diff
```

5) Run the playbook if all seems to be right

```
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

[Vladimir Botka](https://botka.link)
