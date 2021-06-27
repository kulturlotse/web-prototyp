# Development

## Local MySQL Setup

First you need to setup a MySQL server for your system. See the
[MySQL installation guide](https://dev.mysql.com/doc/mysql-installation-excerpt/5.7/en/)
for installation instructions.

Dump an existing remote DB with
```
$ mysqldump -u <READONLY_USER> -h <DB_HOST> -p <DB_NAME> --skip-lock-tables --column-statistics=0 > <DB_NAME>.sql
```

Create a local database:
```
$ mysql -p --execute "CREATE DATABASE <DB_NAME>"
```

Load the dump
```
mysql -p <DB_NAME> < <DB_NAME>.sql
```
