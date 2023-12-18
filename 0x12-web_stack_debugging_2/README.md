# 0x12. Web stack debugging #2 - Project README

## Overview
This repository contains the answer files for the "0x12. Web stack debugging #2" project, focusing on debugging and fixing issues in web server configurations.

## Concepts
The primary concept covered in this project is "Web stack debugging."

## Requirements
- All files are interpreted on Ubuntu 20.04 LTS.
- Files should end with a new line.
- A `README.md` file at the root of the project folder is mandatory.
- All Bash script files must be executable.
- Bash scripts must pass Shellcheck without any error.
- Bash scripts must run without error.
- The first line of all Bash scripts should be `#!/usr/bin/env bash`.
- The second line of all Bash scripts should be a comment explaining the script's purpose.

## Task Details

### 0. Run software as another user (mandatory)
#### Requirements:
- Write a Bash script that accepts one argument.
- The script should run the `whoami` command under the user passed as an argument.
- Test the script with different users.

#### Example:
```bash
root@ubuntu:~# whoami
root
root@ubuntu:~# ./0-iamsomeoneelse www-data
www-data
root@ubuntu:~# whoami
root
root@ubuntu:~#
```

#### Repository Details:
- GitHub Repository: [alx-system_engineering-devops](https://github.com/Manalhub/alx-system_engineering-devops)
- Directory: 0x12-web_stack_debugging_2
- File: [0-iamsomeoneelse](alx-system_engineering-devops/0x12-web_stack_debugging_2/0-iamsomeoneelse)

### 1. Run Nginx as Nginx (mandatory)
#### Requirements:
- Configure the container to run Nginx as the `nginx` user.
- Nginx should listen on all active IPs on port 8080.
- Write a Bash script to achieve the above requirements.

#### After Debugging:
```bash
root@ab6f4542747e:~# ps auxff | grep ngin[x]
nginx      884  0.0  0.0  77360  2744 ?        Ss   19:16   0:00 nginx: master process /usr/sbin/nginx
nginx      885  0.0  0.0  77712  2772 ?        S    19:16   0:00  \_ nginx: worker process
nginx      886  0.0  0.0  77712  3180 ?        S    19:16   0:00  \_ nginx: worker process
nginx      887  0.0  0.0  77712  3180 ?        S    19:16   0:00  \_ nginx: worker process
nginx      888  0.0  0.0  77712  3208 ?        S    19:16   0:00  \_ nginx: worker process
root@ab6f4542747e:~#
root@ab6f4542747e:~# nc -z 0 8080 ; echo $?
0
root@ab6f4542747e:~#
```

#### Repository Details:
- GitHub Repository: [alx-system_engineering-devops](https://github.com/Manalhub/alx-system_engineering-devops)
- Directory: 0x12-web_stack_debugging_2
- File: [1-run_nginx_as_nginx](alx-system_engineering-devops/0x12-web_stack_debugging_2/1-run_nginx_as_nginx)

### 2. 7 lines or less (advanced)
#### Requirements:
- Shorten the Bash script from Task #1 to 7 lines or less.
- Follow Bash script requirements.
- Do not use `;`, `&&`, `wget`, or execute the previous answer file.

#### Repository Details:
- GitHub Repository: [alx-system_engineering-devops](https://github.com/Manalhub/alx-system_engineering-devops)
- Directory: 0x12-web_stack_debugging_2
- File: [100-fix_in_7_lines_or_less](alx-system_engineering-devops/0x12-web_stack_debugging_2/100-fix_in_7_lines_or_less)
