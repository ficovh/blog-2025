---
layout: post
title: PostgreSQL en Arch Linux
description: Instalando PostgreSQL en Arch Linux 
image: assets/images/postgresql-archlinux.png
---


![database]({{ site.baseurl }}/assets/images/postgresql-archlinux.png)

# Instalando y e iniciando PostgreSQL en Arch Linux

**1.- Instalar PostgreSQL via pacman**

```shell
 sudo pacman -S postgresql 
```

**2.- Ingresar como administrador de PotgreSQL e iniciar el motor de base de datos**

```shell
  $ sudo su - postgres
  [sudo] password for ficovh:

  [postgres@devel ~]$ initdb -D /var/lib/postgres/data
```
**3.- configurar el servicio de PostgreSQL para iniciar automaticamente**

```shell
	$ sudo systemctl enable postgresql
	$ sudo systemctl start  postgresql
```

```shell
  $ sudo su - postgres
  [sudo] password for ficovh:

  [postgres@devel ~]$ psql
  psql (16.3)
  Type "help" for help.
```

**4.- Tareas de administracion, creacion de base de datos, roles, schema (>15)**

```shell

 postgres=# create database customers ;
 CREATE DATABASE
 postgres=# \c customers ;
 You are now connected to database "customers" as user "postgres".
 customers=# create schema admindb authorization admindb ;
 CREATE SCHEMA
 customers=# \q
 [postgres@devel ~]$ exit
 logout
```

Referencias:
* [Learn PostgreSQL - Ferrari](https://www.packtpub.com/en-us/product/learn-postgresql-9781838985288)
* [Sitio oficial de PostgreSQL](https://www.postgresql.org)

