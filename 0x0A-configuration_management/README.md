Project Description
This project is an introduction to configuration management with Puppet. It covers fundamental concepts in DevOps, SysAdmin, Scripting, and CI/CD. The project provides hands-on experience in using Puppet to automate tasks such as creating files, installing packages, and executing commands on Ubuntu 20.04 LTS.

Background Context:

The project's context is inspired by a real-world scenario where automation played a crucial role in restoring a critical infrastructure. Sylvain Kalache shares a story where Puppet was used to recover from a disaster efficiently.

Prerequisites
Before beginning, ensure you have the following prerequisites in place:

Ubuntu 20.04 LTS virtual machine.
Puppet 5.5 preinstalled.
Puppet can be installed using the following commands:

bash
Copy code
$ apt-get install -y ruby=1:2.7+1 --allow-downgrades
$ apt-get install -y ruby-augeas
$ apt-get install -y ruby-shadow
$ apt-get install -y puppet
Additionally, you will need to install puppet-lint:

bash
Copy code
$ gem install puppet-lint
Installation
Clone the GitHub repository for this project:

bash
Copy code
git clone https://github.com/your-username/alx-system_engineering-devops.git
Navigate to the project directory:

bash
Copy code
cd alx-system_engineering-devops/0x0A-configuration_management
You are now ready to start working on the tasks.

Usage
In this section, find information on how to use Puppet to complete the tasks outlined in this project.

Tasks
Task 0: Create a File
Objective: Using Puppet, create a file in the /tmp directory with the following requirements:

File path is /tmp/school
File permission is 0744
File owner is www-data
File group is www-data
File contains the text "I love Puppet"
Example:

bash
Copy code
$ puppet apply 0-create_a_file.pp
Task 1: Install a Package
Objective: Using Puppet, install the Flask package from pip3 with the version 2.1.0.

Example:

bash
Copy code
$ puppet apply 1-install_a_package.pp
Task 2: Execute a Command
Objective: Create a Puppet manifest that kills a process named killmenow using the exec Puppet resource and pkill.

Example:

Terminal #0 - Start a process:

bash
Copy code
$ ./killmenow
Terminal #1 - Execute the Puppet manifest:

bash
Copy code
$ puppet apply 2-execute_a_command.pp

