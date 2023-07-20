#REST #django #guide #python 

# Guide to Serializing and Deserializing 
_________________________________________________________________

## Serializing an Object

Drawing from the example provided in [[Setting up Custom Serializers]], we can now use the `CommentSerializer` to serialize a comment. Again the serializer is reminiscent of using a `Form` in vanilla Django.
```
serializer = CommentSerializer(comment)
serializer.data
# {'email': 'leil@example.com', 'content', 'foo bar', 'created': '2016-01-27T15:17:10.375877'}
```
Now that the comment has been translated into Python native datatypes, we can now render the data into `json`.
```
from rest_framework.renderers import JSONRenderer

json = JSONRenderer().render(serializer.data)
json
# b'{"email":"leila@example.com","content":"foo bar","created":"2016-01-27T15:17:10.375877"}'
```

## Deserializing an Object

To deserialize an object, essentially, you reverse the serialization process. Firstly, parse the `json` into Python native data types:
```
import io
from rest_framework.parsers import JSONParser

stream = io.BytesIO(json)
data = JSONParser().parse(stream)
```

Next we can restore those native datatypes into a dictionary of validated data:
```
serializer = CommentSerializer(data=data)
serializer.is_valid()
# True
serializer.validated_data
# {'content': 'foo bar', 'email': 'leila@example.com','created': datetime.datetime(2012, 08, 22, 16, 20, 09, 822243)}
```

## Resources
[Serializers - Django REST framework (django-rest-framework.org)](https://www.django-rest-framework.org/api-guide/serializers/)
