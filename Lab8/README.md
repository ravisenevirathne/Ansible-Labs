# Lab7 - Create Dev/Prod inventory file

We can easily defined different environments with multiple inventory (hosts) files. In real world we will have different servers defined in these inventory files for Development and Production workloads.

In this lab we will only setup a variable which belong to the environment and it will be called in the application. 

## Test Connectivity for prod 
```
ansible-playbook -i inventories/prod  playbook.yaml 
curl loadbalancer

vagrant@ansible-control:/vagrant/Lab8$ curl loadbalancer
Hello world - from Web01 variable..... I'm Webserver web01
This is the production environment !!!

vagrant@ansible-control:/vagrant/Lab8$ curl loadbalancer
Hello world - from common Variables..... I'm Webserver web02
This is the production environment !!!

```

## Test Connectivity for dev 
```
ansible-playbook -i inventories/dev  playbook.yaml 
curl loadbalancer

vagrant@ansible-control:/vagrant/Lab8$ curl loadbalancer
Hello world - from Web01 variable..... I'm Webserver web01
This is the development environment !!!

vagrant@ansible-control:/vagrant/Lab8$ curl loadbalancer
Hello world - from common Variables..... I'm Webserver web02
This is the development environment !!!

```