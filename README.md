## Postgres

### Install

#### json.pm (osx)

    sudo cpan App::cpanminus

or

    curl -L http://cpanmin.us | perl - _sudo App::cpanminus

### Backup

via Linux

    pg_dump -Fc --no-acl --no-owner -h localhost -U [username] mydb > dump.sql

via OSX & http://postgresapp.com/

    /Applications/Postgres.app/Contents/MacOS/bin/pg_dump -Fc --no-acl --no-owner -h localhost -U [username] mydb > dump.sql

### Restore

    pg_restore --verbose --clean --no-acl --no-owner -h localhost -U [username] -d mydb dump.sql

or

    pg_restore --verbose --clean --no-acl --no-owner -h localhost -U [username] --port 5432 -d mydb dump.sql

via OSX & http://postgresapp.com/

    /Applications/Postgres.app/Contents/MacOS/bin/pg_restore --verbose --clean --no-acl --no-owner -h localhost -U [username] -d mydb dump.sql

### Login

for postgres.app

    psql -h localhost

or

    psql -h localhost --port 5432 -U postgres

### Permissions

    CREATE USER tony WITH PASSWORD 'password';

    ALTER USER tony WITH SUPERUSER;

    CREATE DATABASE mark1;

    GRANT ALL PRIVILEGES ON DATABASE mark1 to tony;

    \q

### MacPorts start / stop

    sudo port load postgresql92-server

    sudo port unload postgresql92-server

alias added for this

   portsql [unload/load]
