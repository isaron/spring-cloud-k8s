### Applying the schema
```
# Barracuda supports compression (In AWS RDS, this must be assigned in a parameter group)
$ mysql -uroot -e "SET GLOBAL innodb_file_format=Barracuda"
# This command should work even in RDS, and return "Barracuda"
$ mysql -uroot -e "show global variables like 'innodb_file_format'"

# install the schema and indexes
$ mysql -uroot -e "create database if not exists zipkin"
$ mysql -uroot -Dzipkin < src/main/resources/mysql_init.sql
```