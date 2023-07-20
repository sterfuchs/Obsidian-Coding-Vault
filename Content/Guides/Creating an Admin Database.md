#guide #django #python #database 

# Getting Started with the Admin Database
________________________________________________________________________

## Creating the Admin Database

Once you define your models, you can use Django to automatically create a professional, production ready [[Django administrative interface]].  This is a website that lets authenticated users to add, change, and delete database objects. The only step required is to register your database model in your admin site:

>`mysite/news/models.py`
```
from django.db import models

class Person(models.Model):
	first_name = models.CharField(max_length=30)
	last_name = models.CharField(max_length=30)
	bill = models.ForeignKey(Bills, on_delete=models.CASCADE)
```
>`mysite/news/admin.py`
```
from django.contrib import admin
from . import models

admin.site.register(models.Person)
```

By completing these steps, you will have successfully set up the database administration interface for your application. This interface allows you to start populating the database with data early on in the development lifecycle. Consequently, you can tailor the presentation of data to meet the requirements of your clients effectively.

## Resources

[The Django admin site | Django documentation | Django (djangoproject.com)](https://docs.djangoproject.com/en/4.2/ref/contrib/admin/)