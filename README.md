# database

## create database

$ mysql -uroot -e 'create database eko_development'
$ mysql -uroot -e 'create database eko_test'
$ mysql -uroot -e 'drop database eko_development'
$ mysql -uroot -e 'drop database eko_test'

## Schema Migration

$ brew install sqldef/sqldef/mysqldef

$ mysqldef -uroot eko_development --dry-run < schema.sql
$ mysqldef -uroot eko_development < schema.sql
$ mysqldef -uroot eko_test --dry-run < schema.sql
$ mysqldef -uroot eko_test < schema.sql

## data seed

$ mysql -uroot eko_development < seed.sql

## ORM

$ brew install sqlboiler

### generate model code from table

MYSQL_DBNAME=eko_development MYSQL_USER=root MYSQL_HOST=127.0.0.1 MYSQL_SSLMODE=false sqlboiler mysql
