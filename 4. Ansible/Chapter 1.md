# **Ansible**

Ansible is an automation engine that allows for agentless system configuration and deployment.

## Ansible Installation and Configuration.

    sudo yum install ansible
    -> install logs

    vim /etc/ansible/ansible.cfg
    -> #inventory = /etc/ansible/hosts (Default)

## Ansible Documentation

https://docs.ansible.com/

## Adhoc Commands

    ansible <HOST> -b -m <MODULE> -a "<ARG1 ARG2 ARG3>"

    [Image4]

## Ansible Playbook

    Ansible playbooks are the primary means for Ansible to perform tasks.
    [Image5]
    [Image6]
    [Image7]

## Ansible Vault



