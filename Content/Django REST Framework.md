#REST #django #extension #python  #moc 

---
name: Django
site: https://www.django-rest-framework.org/
status: learning
topic:
 - Web Development
 - Python
 - Frameworks
 - Extensions
history:
  - 2023-07-20: creation
---
# About Django REST Framework

The Django REST Framework (DRF) is built on top of Django and extends its functionality to specifically address the needs of building Web APIs. It offers a set of tools and components tailored for building RESTful APIs.

## What makes Django REST Framework Different

* Serialization - While the original Django framework has serialization for data formats such as JSON, XML, or YAML, its focuses primarily serializing database records for use in web views or communication with external systems. DRF on the other-hand includes a powerful and flexible serialization framework that can handle complex data structures, nested relationships, and data validation. It goes beyond Django's serialization capabilities and is designed explicitly for serializing data in API responses and handling request data.
* Views vs. Viewpoints: While the original Django handles HTTP  requests and return HTTP responses, DRF introduces the concept of viewsets. Viewsets are high-level abstractions that provide a simplified way to define views for RESTful APIs. Viewsets can handle common CRUD operations and map them to their corresponding HTTP methods (GET, POST, PUT, DELETE).
* Authentication - DRF extends Django's  authentication and permissions system to specifically cater to API authentication. It includes additional authentication schemes like token authentication, OAuth1/2, and JSON Web Tokens. DRF also provides fine-grained permissions that control access to API endpoints based on user roles and permissions. 


## DRF Specific Guides
[[Setting up Custom Serializers]]
[[Serializing and Deserializing]]
## DRF Specific Elements
