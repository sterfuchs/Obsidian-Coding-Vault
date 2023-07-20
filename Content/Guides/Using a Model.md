#guide #django #python #database

# Installing and Utilizing Models
_____________________________________________________
The process of installing and employing Django models in a web application is straightforward and intuitive.

## Installation

To leverage the model in your web application, you must first migrate the new model into your database. This migration can be performed using the command-line interface or terminal as follows:
```
# makemigrations generations migrations for any model that are yet to exist in the
# database

python manage.py makemigrations

# migrate executes all queued migrations and creates the specified tables
python manage.py migrate
```

Other optional yet beneficial commands to execute include:
```
# Print all SQL statements for a migration
python manage.py sqlmigrate

# Displays all the migrations associated with the project along with their status
python manage.py showmigrations
```


## Model Utilization 

Following the creation of data models, Django offers you a database-abstraction API that enables you to perform Create, Read, Update, and Delete (CRUD) operations effortlessly.

```
# Import models we migrated
>>> from myapp.models import Person, Bills

# No Person instance has been added to the system yet
>>> Person.objects.all()
<QuerySet []>

# Instantiate a new Person
>>> p = Person(first_name="Sterling", last_name="Fuchs")

# Store the 'Person' instance into the database
>>> p.save()

# Now you can call its automatically generated id
>>> p.id
1

# Now the new Person is in the database
>>> Person.objects.all()
<QuerySet [<Person: Sterling Fuchs>]>

>>> p.first_name
'Sterling'

>>> Person.objects.get(id=1)
<Person: Sterling Fuchs>

>>> Person.objects.get(first_name__startswith="Ster")
<Person: Sterling Fuchs>

>>> Person.objects.get(first_name__contains="rlin")
<Person: Sterling Fuchs>

>>> Person.objects.get(id=2)
Traceback (most recent call last):
    ...
DoesNotExist: Person matching query does not exist.

>>> b = Bills(name:"Water Utilities", amount=100, owner=p)
>>> b.save()

# Now the bill is in the database
>>> Article.objects.all()
<QuerySet [<Bill: Water Utilities>]>

# Database objects get access to related objects
>>> p = b.owner
>>> p.first_name
'Sterling'

>>> p.bill_set.all()
<QuerySet [<Bills: Water Utilities>]>

#All SQL is done behind the scenes
>>> Bills.objects.filter(person__first_name__startswith="Ster")
<QuerySet [<Bills: Water Utilities>]>

#Delete an object
p.delete()
```

## Resources

[Models | Django documentation | Django (djangoproject.com)](https://docs.djangoproject.com/en/4.2/topics/db/models/)