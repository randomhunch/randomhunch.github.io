---
layout: post
title: "Postgres Installation and Configuration"
date: 2020-10-10 23:37:00 -0400
categories: Technology Database
---

# Postgres Installation
```console
$ sudo apt update
$ sudo apt install postgresql postgresql-contrib
```
# Configuration
## Switch to postgres account
```console
$ sudo -i -u postgres
$ psql
postgres=# \q
```
## Run Postgres without switching account
```console
$ sudo -u postgres psql
postgres=# \q
```
