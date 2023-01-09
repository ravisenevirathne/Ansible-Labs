# Lab6 - Using Tags
<br>
    Tags allow you to categorize item in the playbook and tasks. Helpful on large playbooks as it allows you to run specific part of playbook as needed.
    - Use `--list-tags` to see the current tags 
    - Use `always` keyword for common tasks
    - Run playbooks using tags to only run certain items

## To view current tags
```
ansible-playbook -i hosts playbook.yaml --list-tags
```

## Run playbook with specific tags
```
ansible-playbook -i hosts playbook.yaml --tags configuration
ansible-playbook -i hosts playbook.yaml --tags proxy
```

## you can run multiple tag items as below
```
ansible-playbook -i hosts playbook.yaml --tags installation,configuration
```

## Test Connectivity to webservers
```
ansible-playbook -i hosts playbook.yaml 
curl web01:8000
curl web02:8000
curl loadbalancer
```
