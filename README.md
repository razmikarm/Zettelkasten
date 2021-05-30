# Zettelkasten
Tool for storing and sorting data

# Steps to install

### Basic packages (Ubuntu 20.04 / Python 3.8)

> sudo apt update && sudo apt upgrade

> sudo apt install python3-dev libpq-dev postgresql postgresql-contrib

> python -m pip install virtualenv

### PostgreSQL setup

> sudo -u postgres psql

> CREATE DATABASE `db_name_here`;

> CREATE USER `db_user_here` WITH PASSWORD `db_pass_here`;

> ALTER ROLE `db_user_here` SET client_encoding TO 'utf8';

> ALTER ROLE `db_user_here` SET default_transaction_isolation TO 'read committed';

> ALTER ROLE `db_user_here` SET timezone TO 'UTC';

> GRANT ALL PRIVILEGES ON DATABASE zettelkasten TO `db_user_here`;

> \q

### Python environment

> cd Zettelkasten

> python -m virtualenv venv

#### `Note:` We store our security data in separate file, to prevent access from `settings.py`
> `exports.sh`
> 
>> export SECRET_KEY='`secret_key_here`'
>>
>> export DB_NAME='`db_name_here`'
>> 
>> export DB_USER='`db_user_here`'
>> 
>> export DB_PASS='`db_pass_here`'
>> 
>> export DB_HOST='`db_host_here`'
>> 
>> export DB_PORT='`db_port_here`'
 
> ln -s exports.sh venv/bin/exports.sh

> echo '. exports.sh' >> venv/bin/activate

> . venv/bin/activate

> pip install -r requirements.txt

# Running server

> cd zettelkasten

> ./manage.py runserver