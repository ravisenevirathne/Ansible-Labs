# Lab4 - Separate tasks and handlers to different folders
    Here we the same code from Lab3 and separate taska and handlers to separate subfolders, which make main playbook simple and easy to read.
    This practice allow to create playbooks with reusable codes

## Run playbook from ansible-control 
```
ansible-playbook -i hosts playbook.yaml
```

## Test Connectivity to webservers
```
curl web01:8000
curl web02:8000
```