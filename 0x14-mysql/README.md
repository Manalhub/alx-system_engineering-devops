# 0x14. MySQL - Project README

## Overview
This repository contains the answer files for the "0x14. MySQL" project, focusing on MySQL database administration, replication, and backup strategies.

## Concepts
The primary concepts covered in this project include:
- Database administration
- Web stack debugging
- [How to] Install MySQL 5.7

## Resources
Read or watch:
- What is a primary-replica cluster
- MySQL primary replica setup
- Build a robust database backup strategy

## Learning Objectives
At the end of this project, you are expected to be able to explain:
- The main role of a database
- What a database replica is and its purpose
- Why database backups need to be stored in different physical locations
- The operation to regularly perform to ensure a database backup strategy works

## Requirements
### General
- Allowed editors: vi, vim, emacs
- All files interpreted on Ubuntu 16.04 LTS
- Files should end with a new line
- A `README.md` file at the root of the project folder is mandatory
- All Bash script files must be executable
- Bash scripts must pass Shellcheck without any error
- The first line of all Bash scripts should be `#!/usr/bin/env bash`
- The second line of all Bash scripts should be a comment explaining the script's purpose

### Your Servers
| Name             | Username | IP              | State   |
|------------------|----------|------------------|---------|
| 368069-web-01    | ubuntu   | 100.26.247.57   | running |
| 368069-web-02    | ubuntu   | 100.25.151.74   | running |
| 368069-lb-01     | ubuntu   | 54.152.53.211   | running |

## Task Details

### 0. Install MySQL (mandatory)
- MySQL distribution must be 5.7.x
- Ensure that task #3 of your SSH project is completed for web-01 and web-02.

#### Example:
```bash
ubuntu@229-web-01:~$ mysql --version
mysql  Ver 14.14 Distrib 5.7.25, for Linux (x86_64) using  EditLine wrapper
ubuntu@229-web-01:~$
```

#### Repository Details:
- GitHub Repository: [alx-system_engineering-devops](https://github.com/Manalhub/alx-system_engineering-devops)
- Directory: [0x14-mysql](https://github.com/Manalhub/alx-system_engineering-devops/0x14-mysql)

### 1. Let us in! (mandatory)
- Create a MySQL user named holberton_user on both web-01 and web-02.
- Set the host name to localhost and the password to projectcorrection280hbtn.
- Ensure that holberton_user has permission to check the primary/replica status of your databases.
- Make sure that task #3 of your SSH project is completed for web-01 and web-02.

#### Example:
```bash
ubuntu@229-web-01:~$ mysql -uholberton_user -p -e "SHOW GRANTS FOR 'holberton_user'@'localhost'"
Enter password:
+-----------------------------------------------------------------+
| Grants for holberton_user@localhost                             |
+-----------------------------------------------------------------+
| GRANT REPLICATION CLIENT ON *.* TO 'holberton_user'@'localhost' |
+-----------------------------------------------------------------+
ubuntu@229-web-01:~$
```

#### Repository Details:
- GitHub Repository: [alx-system_engineering-devops](https://github.com/Manalhub/alx-system_engineering-devops)
- Directory: [0x14-mysql](https://github.com/Manalhub/alx-system_engineering-devops/0x14-mysql)

### 2. If only you could see what I've seen with your eyes (mandatory)
- Create a database named tyrell_corp.
- Create a table named nexus6 within the tyrell_corp database.
- Add at least one entry to the nexus6 table.
- Ensure that holberton_user has SELECT permissions on your table.

```bash
ubuntu@229-web-01:~$ mysql -uholberton_user -p -e "use tyrell_corp; select * from nexus6"
Enter password:
+----+-------+
| id | name  |
+----+-------+
|  1 | Leon  |
+----+-------+
ubuntu@229-web-01:~$
```

#### Repository Details:
- GitHub Repository: [alx-system_engineering-devops](https://github.com/Manalhub/alx-system_engineering-devops)
- Directory: [0x14-mysql](https://github.com/Manalhub/alx-system_engineering-devops/0x14-mysql)

### 3. Quite an experience to live in fear, isn't it? (mandatory)
- On web-01, create a new user for the replica server named replica_user.
- The name should be set to %, and set any password.
- Ensure that replica_user has the appropriate permissions to replicate your primary MySQL server.
- Verify that holberton_user has SELECT privileges on the mysql.user table.

```bash
ubuntu@229-web-01:~$ mysql -uholberton_user -p -e 'SELECT user, Repl_slave_priv FROM mysql.user'
+------------------+-----------------+
| user             | Repl_slave_priv |
+------------------+-----------------+
| root             | Y               |
| mysql.session    | N               |
| mysql.sys        | N               |
| debian-sys-maint | Y               |
| holberton_user   | N               |
| replica_user     | Y               |
+------------------+-----------------+
ubuntu@229-web-01:~$
```

#### Repository Details:
- GitHub Repository: [alx-system_engineering-devops](https://github.com/Manalhub/alx-system_engineering-devops)
- Directory: [0x14-mysql](https://github.com/Manalhub/alx-system_engineering-devops/0x14-mysql)

### 4. Setup a Primary-Replica infrastructure using MySQL (mandatory)
- MySQL primary must be hosted on web-01.
- MySQL replica must be hosted on web-02.
- Setup replication for the MySQL database named tyrell_corp.
- Provide your MySQL primary configuration as the answer file (my.cnf or mysqld.cnf) with the name 4-mysql_configuration_primary.
- Provide your MySQL replica configuration as the answer file with the name 4-mysql_configuration_replica.

#### Tips:
- Once MySQL replication is set up, add a new record in your table via MySQL on web-01 and check if the record has been replicated in MySQL web-02.

#### Repository Details:
- GitHub Repository: [alx-system_engineering-devops](https://github.com/Manalhub/alx-system_engineering-devops)
- Directory: [0x14-mysql](https://github.com/Manalhub/alx-system_engineering-devops/0x14-mysql)
- Files: [4-mysql_configuration_primary](https://github.com/Manalhub/alx-system_engineering-devops/0x14-mysql/4-mysql_configuration_primary), [4-mysql_configuration_replica](https://github.com/Manalhub/alx-system_engineering-devops/0x14-mysql/4-mysql_configuration_replica)

### 5.

 MySQL backup (mandatory)
- Write a Bash script that generates a MySQL dump and creates a compressed archive out of it.
- The MySQL dump must contain all your MySQL databases.
- The MySQL dump must be named backup.sql.
- The MySQL dump file has to be compressed to a tar.gz archive.
- This archive must have the following name format: day-month-year.tar.gz.
- The user to connect to the MySQL database must be root.
- The Bash script accepts one argument that is the password used to connect to the MySQL database.

#### Example:
```bash
ubuntu@03-web-01:~$ ls
5-mysql_backup
ubuntu@03-web-01:~$ ./5-mysql_backup mydummypassword
backup.sql
ubuntu@03-web-01:~$ ls
01-03-2017.tar.gz  5-mysql_backup  backup.sql
ubuntu@03-web-01:~$ more backup.sql
-- MySQL dump 10.13  Distrib 5.7.25, for debian-linux-gnu (x86_64)
-- ...
--  Rest of the MySQL dump content
-- ...
ubuntu@03-web-01:~$ file 01-03-2017.tar.gz
01-03-2017.tar.gz: gzip compressed data, from Unix, last modified: Wed Mar  1 23:38:09 2017
ubuntu@03-web-01:~$
```

#### Repository Details:
- GitHub Repository: [alx-system_engineering-devops](https://github.com/Manalhub/alx-system_engineering-devops)
- Directory: [0x14-mysql](https://github.com/Manalhub/alx-system_engineering-devops/0x14-mysql)
- File: [5-mysql_backup](https://github.com/Manalhub/alx-system_engineering-devops/0x14-mysql/5-mysql_backup)
