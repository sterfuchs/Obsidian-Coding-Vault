#guide #django #python #html

# Creating a new HTML Template
___________________________________________________________________


## Design a new Template

Django employs a template search path, which enables developers to reduce redundancy across the site's templates. To dictate where Django should seek your templates, it's necessary to first alter your Django DIR settings. Multiple directories can be specified, and Django will look for a matching template based on the order of these listed directories.

For the example in [[Creating a Django View]], let's say the bills/year_archive.py template was found.  Here's a potential layout for the template:

>`bills/year_archive.html`
```
{% extends "base.html" %}

{% block title %}Bills for {{ year }}{% endblock %}

{% block content %}
<h1>Bills for {{ year }}</h1>

{% for bills in bills_list %}
	<p>{{ bills.name }}</p>
	<p>By {{ bills.person.first_name }}</p>
	<p>Published {{ bills.pub_date|date:"F j, Y" }}</p>
{% endfor %}
{% endblock %}
```

Note that variables are surrounded by double curly braces. For instance, `{{ bills.name }}` calls the output of the value of the bill's name attribute. In this context, dots can be used for more than attribute lookup. They are also used to perform dictionary-key lookup, index lookup, and function calls. 

Also, be aware that this template relies on the `base.html` to provide context for this view. This is known as 'template inheritance'. It allows developers to implement wide-ranging changes to a website's styling by merely altering the `base.html`. It also offers the flexibility to create distinct bases for different needs, such as for a mobile and desktop site.

Here is an example of a simple `base.html` file:

>`mysite/templates/base.html`
```
{% load static %}
<html>
<head>
	<title>{% block title %}{% endblock %}</title>
</head>
<body>
	<img srve ="{% static 'images/sitelogo.png' %}" alt="Logo">
	{%block content %}{% endblock %}
</body>
</html>
```

## Resources
[Django at a glance | Django documentation | Django (djangoproject.com)](https://docs.djangoproject.com/en/4.2/intro/overview/#design-your-templates)