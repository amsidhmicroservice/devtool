```
  docker run -d --name postgres-db -e "POSTGRES_PASSWORD=secret" -e "POSTGRES_DB=customerdb" -p 5432:5432 postgres:latest

```