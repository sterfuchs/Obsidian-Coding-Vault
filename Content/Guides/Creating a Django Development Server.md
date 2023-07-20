#guide #django #python 

# Development Server Creation
____________________________________________________

## Creating the Development Server

First, make sure you are in the outer directory of your site's project. Next run the following command:

`$ python manage.py runserver`

If successful, you should see the following output in the terminal:
```
Performing system checks...

System check identified no issues (0 silenced).

You have unapplied migrations; your app may not work properly until they are applied.
Run 'python manage.py migrate' to apply them.

July 19, 2023 - 15:50:53
Django version 4.2, using settings 'mysite.settings'
Starting development server at [http://127.0.0.1:8000/](http://127.0.0.1:8000/)
Quit the server with CONTROL-C.
```

>Note: Ignore the warning about unapplied migrations. You will create your models and migrate them after creating the Development Server. Check out [[Using a Model]] for more information.

You have now started the lightweight development web server. This server is included so you don't have to start the finicky process of setting up an actual web production server  (e.g. Apache) until you are production ready. 

>Note: Don't use this server in anything resembling a production environment. This server is only meant for use while developing/testing.

After the server starts running, visit http://127.0.0.1:8000/ with the web browser. You should see a "Congratulations!" page.

## Resources
[Writing your first Django app, part 1 | Django documentation | Django (djangoproject.com)](https://docs.djangoproject.com/en/4.2/intro/tutorial01/)