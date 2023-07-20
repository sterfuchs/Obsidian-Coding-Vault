#django #python #element

# Glossary

## Folders
`mysite/` - The outer root directory of your site.  Serves as a container to your whole Django Project. Since Django does not rely of this folder's name for identification; you can rename it whatever you want. Created after [[Creating a Django Project]].

`mysite/mysite/` - The inner directory is the actual Python package for your project. Its name is the Python package name you'll need to use to import anything inside it. Created after [[Creating a Django Project]].

## Files
`mysite/mysite/manage.py` - [[Manage.py]] is a command-line utility  that lets you interact with your Django app as an admin. It serves as an alternative to using the `django-admin`  command, while also setting the `DJANGO_SETTINGS_MODULE` environment variable so that it points to the project's manage.py. Created after [[Creating a Django Project]].

`mysite/mysite/__init__.py`: This file tells Python that this directory should be considered a Python package. Created after [[Creating a Django Project]].

`mysite/mysite/settings.py`: Settings/configuration for this project. [[Django Settings]] has more information on specific settings you can set in the file.  Created after [[Creating a Django Project]].

`mysite/mysite/urls.py`: The URL declarations for this Django project. Serves as a "Table of Contents" for the website. You can learn more about URLs in [[Django URL Dispatcher]]. Created after [[Creating a Django Project]].

`mysite/mysite/asgi.py`: An entry point for ASGI-compatible web servers. Created after [[Creating a Django Project]].

`mysite/mysite/asgi.py`: An entry point for WSGI-compatible web servers. Created after [[Creating a Django Project]].


## Resources 

[Writing your first Django app, part 1 | Django documentation | Django (djangoproject.com)](https://docs.djangoproject.com/en/4.2/intro/tutorial01/)
[django-admin and manage.py | Django documentation | Django (djangoproject.com)](https://docs.djangoproject.com/en/4.2/ref/django-admin/)
