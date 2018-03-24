## Lesson 4 - Database
### Description
This lesson is devoted to databases.
Next packages will be installed here:
* flask-sqlalchemy;
* flask-migrate.

### Command for command line
* `flask db init` -- initialize database;
* `flask db migrate -m "<short description>"` -- create migration script that
  will be autofilled by alembic;
* `flask db upgrade` -- upgrade database using rendered scripts;
* `flask db downgrade` -- downgrade from the last migration;

### DB models attributes and methods
* `session` - top-level attribute to work with data within the session;
* `add(<a thing>)` - a thing that will be added to the database;
* `query` - an attribute to run database queries;
** `all()` - retrieve all objects;
** `get(<id>)` - retrieve a DB object by its ID;
* `delete(<a thing>)` - a thing that will be deleted from the database
* `commit()` - commit changes within the database.
