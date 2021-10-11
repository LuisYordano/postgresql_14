# Demo PostgreSQL 14
# Youtube : https://youtu.be/EAoPoCuyoQE
#
# Install PostgreSQL
```bash
docker run --name tutorial -p 5433:5432 -e POSTGRES_PASSWORD=mysecretpassword -d postgres
```

# Create Database for API
```bash
docker exec -it tutorial psql -U postgres
```
```sql
create schema api;
```

```sql
create table api.todos (
  id serial primary key,
  done boolean not null default false,
  task text not null 
);
```

```sql
insert into api.todos (task) values
  ('learn postgrestsql 14'), ('write article .net 6');
```

```sql
select * from api.todos;
```
