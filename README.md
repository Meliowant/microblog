## Lesson 4 - Database
### Description
This lesson is devoted to databases.
Next packages will be installed here:
* flask-sqlalchemy;
* flask-migrate.

### Activation
Add to the app's `__init.py__` file next lines:
```
from flask_sqlalchemy import SQLAlchemy
from flask_migrate import Migrate

...
db = SQLAlchemy(app)  # After initializing app
migrate = SQLAlchemy(app)
```

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
  * `all()` - retrieve all objects;
  * `get(<id>)` - retrieve a DB object by its ID;
* `delete(<a thing>)` - a thing that will be deleted from the database;
* `commit()` - commit changes within the database.

## Lesson 5 - User's login
### Description
This lesson is about user authentication.
Next package will be instaled here:
* flask-login

### Activation
Add to the app's `__init.py__` file next lines:
```
from flask_login import LoginManager
...
login = LoginManager(app)  # After initializing app
```

### Flask-login attributes
* `is_authenticated` - a property, that returns True if a user is
  authenticated;
* `is_active` - a property, if user's account is active;
* `is anonymous` - a property that is False for regular users, True -
  otherwise;
* `get_id()` - a method that returns a unique string identificator for a user.


### Werkzeug.url attributes
* `url_parse` - validates if URL delongs to the same site.

### WTForms hacks
WTForms takes methods `validate_<field_name>` as custom validators and invokes
them in addition to the stock validators.

## Lesson 6 - User profiles
### Description
This lesson is about adding user profiles with avatars etc.
What will be changes:
* Added avatars from Gravatar service;
* Introduced Jinja 2 sub-templates that allow to use the same template for atomic items. 
  Usage: `{% include '<template>' %}`;
* Adding fields "about me" and "last seen" (revise using `flask db migration`
  and `flask db upgrade`).
  
## Lesson 7 - Error handling
### Description
This lesson is about debug mode. To enable it set `FLASK_DEBUG` to `1`.

### Decorators
* `@app.errorhandler(<error_code>)`    calls on error with the appropriate `<error_code>`

### Module `logging`
#### Levels:
* `DEBUG`;
* `INFO`;
* `WARNING`;
* `ERROR`;
* `CRITICAL`.

### Sending errors by mail
* Requries `logging` module (`SMTPHandler` class);
* Requries e-mail settings;

### Recording errors to the file
* Requires `logging` midule (`RotatingFileHandler` class);

