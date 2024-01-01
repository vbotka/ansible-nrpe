=============================
vbotka.nrpe 2.5 Release Notes
=============================

.. contents:: Topics


2.5
===

Release Summary
---------------

Update to Ansible 2.15. By default, dont touch nrpe.cfg and log
file. Add nrpe.conf.d

Major Changes
-------------
* Update to Ansible 2.15

Minor Changes
-------------
* Add nrpe.conf.d
* Update vars/main.yml.sample
* Update README
* Tags renamed -/
* Unified formatting of strings

Bugfixes
--------

Breaking Changes / Porting Guide
--------------------------------
* By default, do not touch log file. Enable nrpe_log_file_enable=true
  if you want to create the log file. Optionally, configure newsyslog
  in vbotka.freebsd_postinstall
* By default, in /usr/local/etc, copy nrpe.cfg.sample to nrpe.cfg if
  missing, but make no changes (default nrpe_conf=[])
