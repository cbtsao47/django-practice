## Lesson Learned:

---

- `pipenv --three`
  - make sure pipenv is using python3 (pipenv is pretty much like npm/yarn)
- `pipenv shell`
  - activate pipenv (virtual env)
- `pipenv install django`
  - install django
- `django-admin startproject [name_of_project]`
  - making a django project
- `django-admin startapp [name_of_app]`
  - making a django app
- `./manage.py runserver [port]`
  - runs server at the port, defaults to 8000
- `./manage.py sqlmigrate [package_name] [migration_id]`
  - run specific migration
- `./manage.py migrate`
  - run all migration

---

## To update a table

- set up tabel

```
class Notes(models.Model):
    id=models.UUIDField(primary_key=True,default=uuid4,editable=False)
    title= models.CharField(max_length=200)
    content=models.TextField(blank=True)
```

- `./manage.py makemigrations`
  - make migrateions based on tables
- `./manage.py migrate`
  - run the migrateions

## python-decouple (like dotenv for javascript)

- `pipenv install python-decouple`

  - install

- `from decouple import config`
  - import
- API_KEY = config('API_KEY')
  - access .env file for something called "API_KEY" and save it as the local variable API_KEY
- DEBUG = config('DEBUG', cast=bool)

  - `cast=bool` means to change the type it's getting from .env to a boolean

* create new secret key

```
import random
''.join([random.SystemRandom().choice('abcdefghijklmnopqrstuvwxyz0123456789!@#$%^&*(-_=+)') for i in range(50)]) # All one line!
```
