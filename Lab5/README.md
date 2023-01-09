# Lab5 - Roles using Ansible Galaxy
    Ansible galaxy provides an framework for creating own roles

## Create Apache2 Role and then move taks, handlers, templates to new roles/apache2 structure. 
```
ansible-galaxy init roles/apache2
# then move relavant tasks, handlers & templates to new roles/apache2 structure
ansible-playbook -i hosts playbook.yaml
```

## Create two new roles called "common" and "nginx", then add nessary files to relavent tasks and handlers folders
```
ansible-galaxy init roles/common
ansible-galaxy init roles/nginx
```

## Test Connectivity to webservers
```
ansible-playbook -i hosts playbook.yaml 
curl web01:8000
curl web02:8000
curl loadbalancer
```