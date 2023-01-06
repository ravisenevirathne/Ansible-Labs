# Lab3 - Simple playbook to configure apache on webservers

## Run playbook from ansible-control 
```
ansible-playbook -i hosts playbook.yaml
```

## Test Connectivity to webservers
```
curl web01:8000
curl web02:8000
```