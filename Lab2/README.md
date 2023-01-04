# Lab2 - Modules and tasks

## APT module to install services
```
    ansible all -i hosts --become -m apt -a "update_cache=yes"
    ansible webservers -i hosts --become -m apt -a "name=apache2 state=present"
    ansible database -i hosts --become -m apt -a "name=mysql-server state=present"
``` 

## Service module to manage services
```
    ansible database --become -i hosts -m service -a "name=mysql state=started"
    nsible database --become -i hosts -m service -a "name=mysql state=restarted"
```

## Reboot webstack
```
    ansible webstack -i hosts --become -m command -a "reboot --reboot"
    ansible webstack -i hosts --become -m command -a "uptime"
```