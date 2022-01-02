# Doctrine2-Spatial

[![Build Status](https://travis-ci.org/creof/doctrine2-spatial.svg?branch=master)](https://travis-ci.org/creof/doctrine2-spatial)
[![Code Climate](https://codeclimate.com/github/creof/doctrine2-spatial/badges/gpa.svg)](https://codeclimate.com/github/creof/doctrine2-spatial)
[![Coverage Status](https://coveralls.io/repos/creof/doctrine2-spatial/badge.svg?branch=master&service=github)](https://coveralls.io/github/creof/doctrine2-spatial?branch=master)
[![Downloads](https://img.shields.io/packagist/dm/creof/doctrine2-spatial.svg)](https://packagist.org/packages/creof/doctrine2-spatial)
[![Gitter](https://badges.gitter.im/gitterHQ/gitter.svg)](https://gitter.im/creof/doctrine2-spatial)


Doctrine2 multi-platform support for spatial types and functions. Currently MySQL and PostgreSQL with PostGIS are supported. Could potentially add support for other platforms if an interest is expressed.

Documentation can be found at [here](./doc/index.md)

Add it in your app/config yml files
```yaml
doctrine:
    dbal:
        types:
            point: Viny\PointType
        default_connection: default
        connections:
            default:
                driver: pdo_mysql
                host: '%database_host%'
                port: '%database_port%'
                dbname: '%database_name%'
                user: '%database_user%'
                password: '%database_password%'
                charset: UTF8
                mapping_types:
                    point: point
```

Symfony Normalization is supported, just add the tag in your app/services yml file
```yaml
services:
  Viny\PointNormalizer:
    tags: ['serializer.normalizer']
