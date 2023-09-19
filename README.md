# Elastic auditd_manager Integration Configuration File Base
This repository contains my tuned (for detection engineering, NOT production) auditd_manager configuration (mostly originating from Neo23x0's Auditd configuration available at https://github.com/Neo23x0/auditd/blob/master/audit.rules).

## Disclaimer
This configuration is mostly a test / detection engineering configuration focused on capturing as much data as possible, and therefore captures A LOT of events. Take this configuration as a base, and remove everything that you do not need. For example, this configuration includes:
```
-w /proc/ -p r -k audit_proc
-w /home/ -p r -k audit_home
-w /usr/bin/ -p r -k audit_usr_bin
-w /bin/ -p r -k audit_bin
-w /etc/ -p rwxa -k audit_recursive_etc
```
Which recursively captures all events in these directories, and thus will generate a lot of documents and take up a lot of space in your cluster. You have been warned. 
