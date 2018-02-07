# MariaDB Docker image running on Alpine Linux

[![Docker Layers](https://img.shields.io/badge/docker%20layers-4-blue.svg?maxAge=2592000?style=flat-square)](https://hub.docker.com/r/yobasystems/alpine-mariadb/) [![Docker Size](https://img.shields.io/badge/docker%20size-50%20MB-blue.svg?maxAge=2592000?style=flat-square)](https://hub.docker.com/r/yobasystems/alpine-mariadb/) [![Docker Stars](https://img.shields.io/docker/stars/yobasystems/alpine-mariadb.svg?maxAge=2592000?style=flat-square)](https://hub.docker.com/r/yobasystems/alpine-mariadb/) [![Docker Pulls](https://img.shields.io/docker/pulls/yobasystems/alpine-mariadb.svg?maxAge=2592000?style=flat-square)](https://hub.docker.com/r/yobasystems/alpine-mariadb/)

[![Alpine Version](https://img.shields.io/badge/alpine%20version-v3.7.0-green.svg?maxAge=2592000?style=flat-square)](http://alpinelinux.org/) [![MariaDB Version](https://img.shields.io/badge/Mariadb%20version-v10.1.28-green.svg?maxAge=2592000?style=flat-square)](https://mariadb.org/)


This Docker image [(yobasystems/alpine-mariadb)](https://hub.docker.com/r/yobasystems/alpine-mariadb/) is based on the minimal [Alpine Linux](https://alpinelinux.org/) with [MariaDB v10.1.28](https://mariadb.org/) (MySQL Compatible) database server.

##### Alpine Version 3.7.0 (Released Nov 30, 2017)
##### MariaDB Version 10.1.28

----

## What is Alpine Linux?
Alpine Linux is a Linux distribution built around musl libc and BusyBox. The image is only 5 MB in size and has access to a package repository that is much more complete than other BusyBox based images. This makes Alpine Linux a great image base for utilities and even production applications. Read more about Alpine Linux here and you can see how their mantra fits in right at home with Docker images.

## What is MariaDB?
MariaDB Server is one of the most popular database servers in the world. It’s made by the original developers of MySQL and guaranteed to stay open source. Notable users include Wikipedia, WordPress.com and Google.

MariaDB turns data into structured information in a wide array of applications, ranging from banking to websites. It is an enhanced, drop-in replacement for MySQL. MariaDB is used because it is fast, scalable and robust, with a rich ecosystem of storage engines, plugins and many other tools make it very versatile for a wide variety of use cases.

MariaDB is developed as open source software and as a relational database it provides an SQL interface for accessing data. The latest versions of MariaDB also include GIS and JSON features.

## Features

  * Minimal size only 48 MB and only 4 layers
  * Memory usage is minimal on a simple install.
  * MariaDB the MySQL replacement


## Architectures

* ```:amd64```, ```:latest``` - 64 bit Intel/AMD (x86_64/amd64)
* ```:i386```, ```:x86``` - 32 bit Intel/AMD (x86/i686)
* ```:arm64v8```, ```:aarch64``` - 64 bit ARM (ARMv8/aarch64)
* ```:arm32v7```, ```:armhf``` - 32 bit ARM (ARMv7/armhf)

#### PLEASE CHECK TAGS BELOW FOR SUPPORTED ARCHITECTURES, THE ABOVE IS A LIST OF EXPLANATION

## Tags

* ```:latest```, ```:amd64``` latest branch based on amd64
* ```:master``` master branch usually inline with latest
* ```:v0.0.0``` version number related to mariadb version
* ```:armhf```, ```:arm32v7``` Armv7 based on latest tag but arm architecture

## Volume structure

* `/var/lib/mysql`: Database files
* `/var/lib/mysql/mysql-bin`: MariaDB logs


## Environment Variables:

### Main Mariadb parameters:
* `MYSQL_DATABASE`: specify the name of the database
* `MYSQL_USER`: specify the User for the database
* `MYSQL_PASSWORD`: specify the User password for the database
* `MYSQL_ROOT_PASSWORD`: specify the root password for Mariadb

> https://mariadb.org/

## Creating an instance


```bash
docker run -it --name mysql -p 3306:3306 -v /var/lib/mysql:/var/lib/mysql -e MYSQL_DATABASE=wordpressdb -e MYSQL_USER=wordpressuser -e MYSQL_PASSWORD=hguyFt6S95dgfR4ryb -e MYSQL_ROOT_PASSWORD=hguyFtgfR4r9R4r76 yobasystems/alpine-mariadb

```

It will create a new db, and set mysql root password (default is RaNd0MpA$$W0Rd generated by pwgen) unless the data already exists.

## Docker Compose example:
####(Please pass your own credentials or let them be generated automatically, don't use these ones for production!!)

```yalm
mysql:
  image: yobasystems/alpine-mariadb
  environment:
    MYSQL_ROOT_PASSWORD: hguyFtgfR4r9R4r76
    MYSQL_DATABASE: wordpressdb
    MYSQL_USER: wordpressuser
    MYSQL_PASSWORD: hguyFt6S95dgfR4ryb
  expose:
    - "3306"
  volumes:
    - /data/example/mysql:/var/lib/mysql
  restart: always
```

## Source Repository

* [Bitbucket - yobasystems/alpine-mariadb](https://bitbucket.org/yobasystems/alpine-mariadb/)

* [Github - yobasystems/alpine-mariadb](https://github.com/yobasystems/alpine-mariadb)

## Links

* [Yoba Systems](https://www.yobasystems.co.uk/)

* [Dockerhub - yobasystems](https://hub.docker.com/u/yobasystems/)

* [Quay.io - yobasystems](https://quay.io/organization/yobasystems)
