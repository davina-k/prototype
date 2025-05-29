# Base Image Installation Ansible Playbook

This repository contains an Ansible playbook designed to automate the installation and configuration of a repeatable base image for C-Disk Linux machines. The goal is to create a clean, consistent environment that can be easily reused across multiple deployments.

The playbook handles essential system setup tasks, including system updates, package installations, security hardening, and basic configuration. It is intended to be idempotent and safe to run multiple times without side effects.

## Prerequisites

To use ansible on your machine, install using either of the below commands
```bash
sudo pip3 install --user ansible
```
or 
```bash
sudo apt install ansible
```

## How to use this playbook: 

To pull down this playbook, navigate to your terminal and run: 
```bash
git clone https://github.com/davina-k/prototype.git
```
to ensure you are in the main branch (production), and using the latest version, always run
```bash
git checkout main
```
```bash
git pull
```

## Usage

Run the playbook from the main folder with:
```bash
ansible-playbook -i inventories/hosts.ini install.yml
```

to run with specific tags such as just a docker install, run with --tags, for example:
```bash
ansible-playbook -i inventories/hosts.ini install.yml --tags docker
```

or to skip certain installs, run with --skip-tags, for example: 
```bash
ansible-playbook -i inventories/hosts.ini install.yml --skip-tags beekeeper
```
