nrpe
====

[![Build Status](https://travis-ci.org/vbotka/ansible-nrpe.svg?branch=master)](https://travis-ci.org/vbotka/ansible-nrpe)

[Ansible role.](https://galaxy.ansible.com/vbotka/nrpe/) Install and configure NRPE.

Nagios Remote Plugin Executor (NRPE)


Requirements
------------

No requiremenst.


Variables
---------

Review defaults and examples in vars.


Workflow
--------

1) Install role.

```
# ansible-galaxy install vbotka.nrpe
```

2) Fit variables.

```
# editor vbotka.nrpe/vars/main.yml
```

3) Create playbook and inventory.

```
# cat nrpe.yml
---
- hosts: webserver
  roles:
    - vbotka.nrpe
```

```
# cat hosts
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

4) Install and configure nrpe.

```
# ansible-playbook nrpe.yml
```

5) TBD ( plugins)
		

References
----------

- [NRPE Manual pdf](http://nagios.sourceforge.net/docs/nrpe/NRPE.pdf)
- [NRPE - Nagios Core Addons](https://assets.nagios.com/downloads/nagioscore/docs/nagioscore/4/en/addons.html#nrpe)
- [How To Install NRPE - FreeBSD](https://support.nagios.com/kb/article.php?id=515#FreeBSD)

License
-------

[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)


Author Information
------------------

[Vladimir Botka](https://botka.link)
