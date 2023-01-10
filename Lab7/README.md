# Lab7 - Ansible Variables

There are two types of variables
-  dynamic variables (`ansible_facts`) automatically gathered by ansible
-  user defined variables

## way to use dynamic variables (ansible_facts)
We can use nodename variable to retrieve hostname dynamically and show it in index.html
```
{{ ansible_facts['nodename'] }}
```

## user defined variables
- common user variables can be defined in `group_vars` folder and will assign to all the hosts
- host specific variables can be defined in `host_vars` folder and use the name of hostname on the yaml file. this will override the group_vars defined variables

## Test Connectivity to webservers
```
ansible-playbook -i hosts playbook.yaml 
curl loadbalancer
vagrant@ansible-control:/vagrant/Lab7$ curl loadbalancer
Hello world - from Web01 variable..... I'm Webserver web01
vagrant@ansible-control:/vagrant/Lab7$ curl loadbalancer
Hello world - from common Variables..... I'm Webserver web02
```
