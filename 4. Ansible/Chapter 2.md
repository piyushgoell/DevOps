# Inventories

It is how Ansible can locate and run against multiple system.  
It is essentially consist of list of hosts.  
By default : /etc/anisble/hosts  
Inventories may be formatted as an INI file or YAML file.
It is possibele to define.
    group of hosts.
    group or host level variables.
    groups of groups.

# Modules

Modules are essentially tools for particular tasks
Modules can take parameters
they return JSON
they canr un from command line or within playbook

# Variable

variable names should be letters, numbers and underscores.
variable should always start with a letter.
can be scoped by group, hosts or even in playbook

can be used to store the return value of executed commands.
can also be dictonaries

# Facts
can provide the infirmation about a given target host
can be discovered by Ansible automatically when it reaches out to a host
Facts gathering may be disabled.
Facts may be cached between playbook executions, this is not a default behaviour. 

# Plays
the goal of a play is to map a group of hosts to some well-defined roles.
a play may use one or more modules to achieve a desired end state on a group of hosts.

# Playbooks

A playbook is a series of plays
A palybook may deploy new web servers, install new application servers and run SQL against database servers to support the new applications.
# Configuration Files
ASIBLE-CONFIG (an environment variable)  
ansible.cfg (in the current directory)  
.ansible.cfg(in the home directory)  
/etc/ansible/ansible.cfg  