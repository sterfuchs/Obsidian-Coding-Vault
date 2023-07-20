#guide #python #django 

# Simple View Creation
_____________________________________________________________________________

## Create a Django View

Each view that you construct in Django has one of two main responsibilities: Either it returns an HttpResponse object containing the page content, or it triggers an exception, such as Http404.

In a majority of situations, a view is responsible for fetching the necessary parameters, loading a relevant template, and rendering that template with the fetched data.
> `mysite/news/views.py`
```
from django.shortcuts import render
from .models import Bills

def year_archive(request, year):
	bills_list = Bills.objects.filter(post_date__year=year)
	context = {"year": year, "bills_list": b_list}
	return render(request, "news/year_archive.html", context)
```
This view leverages a [[Django Template]] to render the web page with the appropriate data.

## Resources
[Django at a glance | Django documentation | Django (djangoproject.com)](https://docs.djangoproject.com/en/4.2/intro/overview/#write-your-views)
