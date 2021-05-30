# Zettelkasten
Tool for storing and sorting data

# Steps to install

### Basic packages (Ubuntu 20.04 / Python 3.8)

> sudo apt update && sudo apt upgrade

> sudo apt install python3-dev libpq-dev postgresql postgresql-contrib

> python -m pip install virtualenv

### PostgreSQL setup

> sudo -u postgres psql

> CREATE DATABASE zettelkasten;

> CREATE USER zettelkasten_user WITH PASSWORD 'ZettelKasten';

> ALTER ROLE zettelkasten_user SET client_encoding TO 'utf8';

> ALTER ROLE zettelkasten_user SET default_transaction_isolation TO 'read committed';

> ALTER ROLE zettelkasten_user SET timezone TO 'UTC';

> GRANT ALL PRIVILEGES ON DATABASE zettelkasten TO zettelkasten_user;

> \q

### Python environment

> cd Zettelkasten

> python -m virtualenv venv

> . venv/bin/activate

> pip install -r requirements.txt

# Running server

> cd zettelkasten

> ./manage.py runserver