# 0x13. Firewall - Project README

## Overview
This repository contains the answer files for the tasks of the "0x13. Firewall" project. The project focuses on configuring and managing firewalls on web servers.

## Concepts
The primary concept covered in this project is "Web stack debugging."

## Background Context
The project addresses the need for setting up a firewall on servers to enhance security. It emphasizes the use of `ufw` (Uncomplicated Firewall) and involves tasks related to blocking incoming traffic and port forwarding.

## Resources
- [What is a firewall](https://en.wikipedia.org/wiki/Firewall_(computing))
- [Web stack debugging guide](https://intranet.hbtn.io/concepts/68)

## Warning
- Containers on demand (Docker) cannot be used for this project.

## Task Details

### 0. Block all incoming traffic
#### Requirements:
- Apply the following configuration to `web-01` (or optionally on `lb-01` and `web-02`).
- Configure `ufw` to block all incoming traffic except the following TCP ports:
  - 22 (SSH)
  - 443 (HTTPS SSL)
  - 80 (HTTP)
- Provide the `ufw` commands used in your answer file.

#### Repository Details:
- GitHub Repository: [alx-system_engineering-devops](https://github.com/Manalhub/alx-system_engineering-devops)
- Directory: 0x13-firewall
- File: [0-block_all_incoming_traffic_but](https://github.com/Manalhub/alx-system_engineering-devops/blob/master/0x13-firewall/0-block_all_incoming_traffic_but)

### 1. Port forwarding (Advanced)
#### Requirements:
- Configure `web-01` to redirect port 8080/TCP to port 80/TCP.
- Provide a copy of the modified `ufw` configuration file.

#### Terminal Commands on `web-01`:
```bash
root@03-web-01:~# netstat -lpn
```

#### Additional Information:
- The web server (nginx) on `web-01` is listening on port 80.
- Use `curl` on `web-02` to test port forwarding.

#### Repository Details:
- GitHub Repository: [alx-system_engineering-devops](https://github.com/your-username/alx-system_engineering-devops)
- Directory: 0x13-firewall
- File: [100-port_forwarding](https://github.com/Manalhub/alx-system_engineering-devops/blob/master/0x13-firewall/100-port_forwarding)
