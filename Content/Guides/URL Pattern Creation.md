#guide #django #python 

# Designing your URLs
______________________________________________

## URLconf Creation

To design URLs for an app, you need to create a Python module called a URLconf. Think of this file as a navigational chart for your application, establishing a linkage between URL patterns and Python callback functions. In addition to this, URLconfs contribute towards uncoupling the URLs from the Python code. For more in-depth documentation on URLs, checkout [[Django URL Dispatcher]].

>`mysite/news/urls.py`
```
from django.urls import path

from . import views

urlspatterns = [
	path("bills/<int:year>/", views.year_archive),
	path("bills/<int:year>/<int:month>/", views.month_archive),
	path("bills/<int:year>/<int:month>/<int:pk>/"), views.bill_detail),
]
```

In the code provided, URL paths are correlated with Python callback functions, also known as "views". The path strings exploit parameter tags to extract values from the URLs. Whenever a user initiates a page request, Django sequentially processes each path and halts at the first one that aligns with the requested URL. If none of the paths match, Django defaults to a specialized 404 view.

Once a pattern coincides with the URL path, Django triggers the specified view (a Python function). This view receives a request object encapsulating metadata, which contains the values extracted from the URL.

## Example

Imagine a scenario where a user wishes to view the details of a specific bill that they have to pay in July 2023. The URL would appear as follows: `/bills/2023/07/13243`. Here, 2023 represents the year, 07 is the month, and 13243 is the unique ID of the bill.

As this URL corresponds to one of the defined URL paths, Django would call the function: `bills.views.bill_detail(request, year=2023, month=7, pk=13243)`


## Resources
[URL dispatcher | Django documentation | Django (djangoproject.com)](https://docs.djangoproject.com/en/4.2/topics/http/urls/)