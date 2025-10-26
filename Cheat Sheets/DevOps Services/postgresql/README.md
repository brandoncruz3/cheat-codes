# postgresql cheatsheet

## External Resources

- https://www.codementor.io/engineerapart/getting-started-with-postgresql-on-mac-osx-are8jcopb
- https://www.tutorialspoint.com/postgresql/postgresql_schema.htm

## Setting Up

Install:

```
brew install postgresql
```

Start:

```
brew services start postgresql
```

Access Postgres:

```
psql postgres
```

## Cheatsheet

Create database:

```
CREATE database foo;
```

Create role:

```
CREATE ROLE user1 WITH LOGIN PASSWORD 'secret';
```

List roles:

```
\du
```

Allow user to create databases:

```
ALTER ROLE user1 CREATEDB;
```

Exit with `\q` and logon with `user1`:

```
psql postgres -U user1
```

Grant all privileges to database:

```
GRANT ALL PRIVILEGES ON DATABASE "foo" to user1;
```

Create user:

```
CREATE USER testuser with encrypted password 'sekretpw';
```

Grant privileges for user:

```
GRANT ALL PRIVILEGES ON database foo TO testuser;
```

Create a auto-incremental column:

```
CREATE TABLE fruits(id SERIAL PRIMARY KEY, name VARCHAR NOT NULL)
INSERT INTO fruits(id,name) VALUES(DEFAULT,'Apple');
```

List databases:

```
\l
```

Switch to database:

```
\c dbname
```

List tables:

```
\dt
\dt+
```

Backup Database:

```
pg_dump -h 127.0.0.1 -U postgres -p 5432 dbname > dbname.bak
```

Restore Database:

```
psql -h dbname.x.eu-west-1.rds.amazonaws.com -U postgres dbname < dbname.bak
```

Resources:

- https://www.digitalocean.com/community/tutorials/how-to-use-roles-and-manage-grant-permissions-in-postgresql-on-a-vps--2
- https://www.postgresqltutorial.com/postgresql-cheat-sheet/
- https://www.postgresqltutorial.com/postgresql-serial/
- https://blog.ruanbekker.com/blog/2019/03/06/create-users-databases-and-granting-access-for-users-on-postgresql/
