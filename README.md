# nrpe

[![Build Status](https://travis-ci.org/vbotka/ansible-nrpe.svg?branch=master)](https://travis-ci.org/vbotka/ansible-nrpe)

[Ansible role.](https://galaxy.ansible.com/vbotka/nrpe/) Install and configure NRPE.

Nagios Remote Plugin Executor (NRPE)

Please feel free to [share your feedback and report issues](https://github.com/vbotka/ansible-nrpe/issues). Contributions are welcome.


## Requirements

None.


## Variables

Review defaults and examples in vars.


## Workflow

1) Install role

```
shell> ansible-galaxy install vbotka.nrpe
```

2) Change variables

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

4) Install packages

```
shell> ansible-playbook nrpe.yml -t nrpe-packages
```

5) Create log

```
shell> ansible-playbook nrpe.yml -t nrpe-log
```

6) Test syntax

```
shell> ansible-playbook nrpe.yml -CD
```

7) Install and configure NRPE

```
shell> ansible-playbook nrpe.yml
```

8) Plugins (TBD)
		

## References

- [NRPE Manual pdf](http://nagios.sourceforge.net/docs/nrpe/NRPE.pdf)
- [NRPE - Nagios Core Addons](https://assets.nagios.com/downloads/nagioscore/docs/nagioscore/4/en/addons.html#nrpe)
- [How To Install NRPE - FreeBSD](https://support.nagios.com/kb/article.php?id=515#FreeBSD)


## License

[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)


## Author Information

[Vladimir Botka](https://botka.link)
