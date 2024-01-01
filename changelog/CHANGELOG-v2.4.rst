=============================
vbotka.nrpe 2.4 Release Notes
=============================

.. contents:: Topics


2.4.1
=====

Release Summary
---------------
By default, dont touch log file. 


Major Changes
-------------

Minor Changes
-------------
* Unified formatting of strings
* Tags renamed -/
* Update README

Bugfixes
--------

Breaking Changes / Porting Guide
--------------------------------
* By default, do not touch log file. Enable nrpe_log_file_enable=true
  if you want to create the log file. Optionally, configure newsyslog
  in vbotka.freebsd_postinstall
