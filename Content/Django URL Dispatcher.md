#django #python #element 

# URL Dispatcher
______________________________________________________________________________

## Overview

To design URLs for an app, you create a Python module informally called a URLconf( More info in [[URL Pattern Creation]]). This mapping can be as short or as long as needed. It can reference other mappings. And, because it’s pure Python code, it can be constructed dynamically.

## Path converters

The following path converters are available by default:
* `str` - Matches any non-empty string, excluding the path separator '/'. This is the default if a converter isn't specified in the expression
* `int` - Matches zero or any positive integer. Returns an `int`
* `slug` - Matches any slug string consisting of ASCII letters or numbers, plus the hyphen and underscore characters. For example `your-1st-django-site`
* `uuid` - Matches a formatted UUID. To prevent multiple URLs from mapping to the same page, dashes must be included and letters must be lowercase. For example, `075194d3-6885-417e-a8a8-6c931e272f00`. Returns a `UUID` instance
* `path` - Matches any non-empty string, including the path separator '/'. This allows you to match against a completed URL instead of just a segment as with `str`

You can allow [[Register Custom Path Converters]]

