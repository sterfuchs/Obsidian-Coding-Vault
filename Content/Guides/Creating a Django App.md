#django #python #guide 

# Creating a Django App
_________________________________________

## Django App Creation

Once you have a project set up, you can start the process of creating the application files that'll serve as your apps main logic base.

Although, you can create your app anywhere along the Python PATH, it is recommended to create your app in the same directory of manage.py. Once within the directory, run the following command in the terminal:

`$ python manage.py startapp bill_payer`

In turn, that'll create a directory `bill_payer`, which should be laid out as follows:
```
bill_payer/
	__init__.py
	admin.py
	apps.py
	migrations/
		__init__.py
	models.py
	tests.py
	views.py
```

## Resources

[Writing your first Django app, part 1 | Django documentation | Django (djangoproject.com)](https://docs.djangoproject.com/en/4.2/intro/tutorial01/)