- Provisions VM's using Vagrant on VirtualBox
    ``` vagrant up 
    ```
- Makesure all VM's are provisioned and running
    ``` vagrant status
    ```
- SSh into Ansible control VM
    ``` vagrant ssh ansible-control
    ```
- sync folder /vagrant is automatically mounted on all VM's. So host files can be access on this location

- Install ansible on ansible-control VM
    ``` sudo apt update
        sudo apt install ansible
    ```
- Make sure ansible is properly running on ansible-control VM
    ``` ansible localhost -m command -a date #this should return the hostname 
    ```
- Add other VM's IP's (as per hosts_file) to /etc/hosts file on ansible-control and check to reach using host name
    ``` vi /etc/hosts
        #update host file with ip's and hostname
        ping db01
    ```

- Setup SSH from ansible-control to other VMs
    ```
    vagrant@ansible-control:/vagrant$ ssh-keygen  #apply all defaults
    vagrant@ansible-control:/vagrant$ ssh-copy-id localhost   # copy locally
    vagrant@ansible-control:/vagrant$ ssh-copy-id web01 && ssh-copy-id web02 && ssh-copy-id loadbalancer && ssh-copy-id db01  # copy to other VMs
    ```

- setup inventory file "hosts" and make sure you can run below command from ansible-host successfully
    ```
    ansible webstack -i hosts -m command -a hostname   #this should return hostnames of all VMs on hosts inventory file
    ```

- Install python simplejson module on all VMs to get the full functionality of ansible
    ```
    ansible all -i hosts -m command -a 'sudo apt-get -y install python-simplejson'
    ```
