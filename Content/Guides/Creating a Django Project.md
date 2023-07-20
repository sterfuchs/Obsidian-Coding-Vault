#guide #django #python 

# Creating a new Django Project
________________________________________________________________

## Creating a Project
Creating a new project using Django is simple. First, using the terminal `cd` into the directory that you want to populate with your web project's files. Next, in the terminal, run this command:
`$ django-admin startproject mysite`

This, in turn, creates a mysite directory in the current directory. 
>NOTE: 
>You need to avoid naming projects after built in Python or Django components.  In particular, this means you should avoid names like Django or test.

After running the above command, you should have a directory that looks similar to this:
```
mysite/
	manage.py
	mysite/
		__init__.py
		settings.py
		urls.py
		asgi.py
		wsgi.py
```

A guide on what each of these files represents can be found at [[Django Files Glossary]]

## Resources
[Writing your first Django app, part 1 | Django documentation | Django (djangoproject.com)](https://docs.djangoproject.com/en/4.2/intro/tutorial01/)