# Useful MySQL Commands

## Basic Commands

Access MySQL prompt: `sudo mysql -u [username] -p`

Show all DBs: `show databases;`

Select DB: `use [database];`

See what DB is in use: `select database();`

Show all tables from current DB: `show tables;`

Show table structure: `describe [table];`


## User Commands

List MySQL users: `select user,host from mysql.user;`

Create `user@host`: `CREATE USER '[username]'@'[IP]' IDENTIFIED BY '[password]';`

Grant `user@host` privileges: `GRANT ALL PRIVILEGES ON [database].[tables] TO '[username]'@'[host]';`

Reload grant tables: `FLUSH PRIVILEGES;`


## Examples

#### Create user `jimlahey` with `localhost` access using password 'MyPassword123!'

`CREATE USER 'jimlahey'@'localhost' IDENTIFIED BY 'MyPassword123!';`

#### Grant user `jimlahey` full access to all tables in the `store_inventory` DB

`GRANT ALL PRIVILEGES ON store_inventory.* TO 'jimlahey'@'localhost';`

`FLUSH PRIVILEGES;`

#### Create user `bubbles` with remote access using password 'MyPassword123!'

`CREATE USER 'bubbles'@'XXX.XXX.XXX.XXX' IDENTIFIED BY 'MyPassword123!';`

#### Grant user `bubbles` full access to all databases and all tables

`GRANT ALL PRIVILEGES ON *.* TO 'bubbles'@'XXX.XXX.XXX.XXX';`

`FLUSH PRIVILEGES;`