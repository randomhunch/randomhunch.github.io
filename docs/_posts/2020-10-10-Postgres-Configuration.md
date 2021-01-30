---
layout: post
title: "Postgres Installation and Configuration"
date: 2020-10-10 23:37:00 -0400
categories: Technology Database
---

## [Postgres Installation][postgres-ubuntu]

```console
$ sudo apt update
$ sudo apt install postgresql postgresql-contrib
```
## Configuration
### Switch to postgres account
```console
$ sudo -i -u postgres
$ psql
postgres=# \q
```
### Run Postgres without switching account
```console
$ sudo -u postgres psql
postgres=# \q
```

### Create new role
```console
sudo -u postgres createuser --interactive
```

### Create new database
```console
sudo -u postgres createdb dbname
```
### Move PostgreSQL Data Directory
```console
$ psql
postgres=# show data_directory

$sudo systemctrl stop postgresql
$sudo systemctrl status postgresql

$sudo rsync -av /var/lib/postgresql /mnt/volume1_nyc1_01/
```
Then edit 
data_directory in postgresql.conf
```
data_directory = '/mnt/volume_nyc1_01/postgresql/12/main'
```
### Allow Remote Access
In file /etc/postgresql/postgresql.conf, add line `listen_addresses = '*'`

In file pg_hba.conf, add line `host all all 0.0.0.0/0`

### Change or set user password
```
alter user zb26 with password 'password';
```

[postgres-ubuntu]: https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-20-04
