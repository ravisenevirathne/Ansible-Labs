# Lab9 - Setup MYSQL Server


## Steps to setup mysql server on db01

- Add python-pip using common installs. make sure to do `update_cache=yes` otherwise this will not work
- using ansible-galaxy create mysql role
```
ansible-galaxy init roles/mysql
```
- create tasks and handlers for mysql role
- run playbook for db01
```
ansible-playbook -i inventories/prod playbook.yaml --tags database
```
- check mysql connectivity
```
vagrant ssh db01
sudo /usr/bin/mysql -u root -p    #password - 12345

mysql> status
--------------
/usr/bin/mysql  Ver 14.14 Distrib 5.7.40, for Linux (x86_64) using  EditLine wrapper

Connection id:          7
Current database:
Current user:           root@localhost
SSL:                    Not in use
Current pager:          stdout
Using outfile:          ''
Using delimiter:        ;
Server version:         5.7.40-0ubuntu0.18.04.1 (Ubuntu)
Protocol version:       10
Connection:             Localhost via UNIX socket
Server characterset:    latin1
Db     characterset:    latin1
Client characterset:    utf8
Conn.  characterset:    utf8
UNIX socket:            /var/run/mysqld/mysqld.sock

mysql> use ravi-db;

mysql> show tables;
+-------------------+
| Tables_in_ravi-db |
+-------------------+
| Persons           |
+-------------------+
1 row in set (0.00 sec)
```

