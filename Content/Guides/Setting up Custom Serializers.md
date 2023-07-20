#django #python #guide #REST

# Creating a Custom Serializer
_______________________________________________________________

## Serializer Creation

Suppose we created a simple object for recording a comment:
```
from datetime import datetime

class Comment:
	def __init__(self, email,  content, created=None)
		self.email = email
		self.content = content
		self.created = created or datetime.now()
comment = Comment(email='leila@example.com', content='foo bar')
```

In order to serialize this object, navigate to your `serializer.py` file to formulate the class that will serve as a serializer for the Comment object. The declaration of a serializer in the Django REST Framework is akin to that of a form.
```
from rest_framework import serializers

class CommentSerializer(serializers.Serializer):
	email = serializers.EmailField()
	content = serializers.CharField(max_length=200)
    created = serializers.DateTimeField()

```

## Resources
[Serializers - Django REST framework (django-rest-framework.org)](https://www.django-rest-framework.org/api-guide/serializers/#declaring-serializers)