#guide #django #python 

# Register Custom Path Converters
____________________________________________________________________

## Creating a Custom Path Converter

When dealing with more intricate match requirements, you might need to construct a custom path converter. This can be achieved by defining your custom path converter in the converters file.

A converter requires:
* A `regex` class attribute, expressed as a string
* A `to_python(self, value)` method. which handles converting the matched string into the type that should be passed to the view function. If the given value cannot be converted, this will trigger a `Value Error`, resulting in a 404 response for the user.
* A `to_url(self, value)` method, which handles converting the Python type into a string to be used in the URL. Like `to_python` it raises a `Value Error` when it cannot convert a given value. As a consequence `reverse()` will raise `NoReverseMatch` unless another pattern matches.

## Example

```
class FourDigitYearConverter:
    regex = "[0-9]{4}"

    def to_python(self, value):
        return int(value)

    def to_url(self, value):
        return "%04d" % value
```

Next, register the custom converter class in your URLconf using the `register_converter()`:

```
from django.urls import path, register_converter

from . import converters, views

register_converter(converters.FourDigitYearConverter, "yyyy")

urlpatterns = [
    path("articles/2003/", views.special_case_2003),
    path("articles/<yyyy:year>/", views.year_archive),
    ...,
]
```

## Resources
[URL dispatcher | Django documentation | Django (djangoproject.com)](https://docs.djangoproject.com/en/4.2/topics/http/urls/)