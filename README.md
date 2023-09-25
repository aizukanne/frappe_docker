[![Build Stable](https://github.com/frappe/frappe_docker/actions/workflows/build_stable.yml/badge.svg)](https://github.com/frappe/frappe_docker/actions/workflows/build_stable.yml)
[![Build Develop](https://github.com/frappe/frappe_docker/actions/workflows/build_develop.yml/badge.svg)](https://github.com/frappe/frappe_docker/actions/workflows/build_develop.yml)

Everything about [Frappe](https://github.com/frappe/frappe) and [ERPNext](https://github.com/frappe/erpnext) in containers. This repo and easy install script have been modified to install
ERPNext with HRMS and Payments applications.

## Easy Install Script
The Easy Install script should get you going with a Frappe/ERPNext setup with minimal manual intervention and effort.
This script uses Docker with the Frappe/ERPNext Docker Repository and can be used for both Development setup and Production setup.

## Getting Started

Download the Easy Install script and execute it:

```sh
wget https://github.com/aizukanne/frappe_docker/blob/main/easy-install.py
python3 easy-install.py --prod --email <email_address_for_SSL> -s <SITENAME> -n <PROJECT>
```
This script will install docker on your system and will fetch the required containers, setup bench and a default ERPNext instance.

The script will generate MySQL root password and an Administrator password for the Frappe/ERPNext instance, which will then be saved under `$HOME/passwords.txt` of the user used to setup the instance.
It will also generate a new compose file under `$HOME/<project-name>-compose.yml`.

When the setup is complete, you will be able to access the system at `http://<your-server-ip>`, wherein you can use the Administrator password to login.

#### Arguments

Here are the arguments for the easy-install script

```txt
usage: easy-install.py [-h] [-p] [-d] [-s SITENAME] [-n PROJECT] [--email EMAIL]

Install Frappe with Docker

options:
  -h, --help            		show this help message and exit
  -p, --prod            		Setup Production System
  -d, --dev             		Setup Development System
  -s SITENAME, --sitename SITENAME      The Site Name for your production site
  -n PROJECT, --project PROJECT         Project Name
  --email EMAIL         		Add email for the SSL.
```
