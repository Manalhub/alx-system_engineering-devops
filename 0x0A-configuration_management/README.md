Project Description

This project is an introduction to configuration management with Puppet. It covers fundamental concepts in DevOps, SysAdmin, Scripting, and CI/CD. The project provides hands-on experience in using Puppet to automate tasks such as creating files, installing packages, and executing commands on Ubuntu 20.04 LTS.

Background Context:

The project's context is inspired by a real-world scenario where automation played a crucial role in restoring a critical infrastructure. Sylvain Kalache shares a story where Puppet was used to recover from a disaster efficiently.

Prerequisites

Ubuntu 20.04 LTS virtual machine.
Puppet 5.5 preinstalled.
Puppet can be installed using the following commands:

bash
Copy code
$ apt-get install -y ruby=1:2.7+1 --allow-downgrades
$ apt-get install -y ruby-augeas
$ apt-get install -y ruby-shadow
$ apt-get install -y puppet
Additionally, you will need to install puppet-lint.
