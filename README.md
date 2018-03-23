## Lesson 4 - Database
### Description
This lesson is devoted to databases.
Next packages will be installed here:
* flask-sqlalchemy
* flask-migrate

### Commands
* `flask db init` -- initialize database
* `flask db migrate -m "<short description>"` -- create migration script that
  will be autofilled by alembic
* `flask db upgrade` -- upgrade database using rendered scripts
