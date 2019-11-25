[![Build Status](https://travis-ci.com/ckaserer/ansible-role-example.svg?branch=master)](https://travis-ci.com/ckaserer/ansible-role-example)
![Maintenance](https://img.shields.io/maintenance/yes/2020)
![GitHub](https://img.shields.io/github/license/ckaserer/ansible-role-example)

# ansible-role-example

We want to develop ansible roles, test their functionality regularly through a CI process and get notifications if compatibility breaks. The validation step should include multiple Linux flavours (e.g. centos/ubuntu/debian) times the supported ansible versions.

The tests should then be executed such that the role is verified with

```
centos:7 + ansible:2.5 + python3.5
centos:7 + ansible:2.5 + python3.6
centos:7 + ansible:2.5 + python3.7
centos:7 + ansible:2.5 + python3.8
centos:7 + ansible:2.6 + ...
centos:7 + ansible:2.7 + ...
...
ubuntu:1604 + ansible:2.5 + ...
ubuntu:1604 + ansible:2.6 + ...
ubuntu:1604 + ansible:2.7 + ...
...
```

In order to test ansible roles with multiple versions of ansible, python and various Linux flavors we can use

* **molecule** for our ansible role functionality
* **docker** as our abstraction layer on which we run the target system for our ansible role
* **tox** to setup generic virtualenvs and test our various combinations without side effects
* **travis** to automate it all
* **slack** for notifications

