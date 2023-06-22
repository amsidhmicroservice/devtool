```
  docker run -d --name mysql-db -e "MYSQL_PASSWORD=tiger" -e "MYSQL_DATABASE=customerdb" -e "MYSQL_ROOT_PASSWORD=tiger" -e "MYSQL_USER=scoot" -p 3306:3306 mysql:5.7

```