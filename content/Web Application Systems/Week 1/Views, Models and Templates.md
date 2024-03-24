## HTTPRequest
In Django, an `HttpRequest` object is created for each request that Django receives. This object contains metadata about the request, including the user making the request, the HTTP method (GET, POST, etc.), headers, and any data sent with the request.
## HTTPResponse
An `HttpResponse` object is what Django returns as a response to a `HttpRequest`. It contains the content that will be displayed to the user, along with HTTP headers and a status code.
## URL Segments
Let's break down https://example.com/blog/posts?post=34 and https://example.com/blog/posts/34

| URL Segment | Description               |
| ----------- | ------------------------- |
| https://    | Protocol                  |
| example.com | domain                    |
| /polls      | Django Application        |
| /posts      | View within application   |
| ?post=34    | Key/Value parameter (GET) |
| /34         | URL Path Parameter        |


## Three Patterns of Views
### Writing Views
```python
from django.http import HttpResponse

def index(request):
	return HttpResponse("Hello, world. You're at the index page")
```
### Multiple Views
You can have multiple views in your Django application. Each view must be defined in our `urls.py` file.

## URL Patterns
URL patterns in Django are how Django determines which view to use for a given `HttpRequest`. These patterns are defined in the `urls.py` file and are written as regular expressions.

Inside the app we need to add this:
```python
# app/urls.py
from django.urls import path
from . import views

urlpatterns = [
	path("", views.index, name="index")
]
```

And in the project we need to add this:
```python
# project/urls.py
from django.urls import include, path
from django.contrib import admin

urlpatterns = [
	path("app/", include("app.urls")),
	path("admin/" admin.site.urls)
]
```
## HTML Response for Views
### CSS
Django views can return HTML responses, which can include CSS for styling. Django's static files feature allows you to serve CSS, JavaScript, and images that are used by your HTML files.

## Data sources
### Models
Models in Django are used to represent data sources. A model is a Python class that inherits from the `django.db.models.Model` class, and represents a database table.

### Creating Models
To create a model, you define a class in models.py and specify the fields for the model. Each field is represented by an instance of a `Field` subclass (e.g., `CharField` for character fields and `IntegerField` for integer fields).

### Interfacing Models
Django provides a high-level, Pythonic interface to your models. You can create, retrieve, update, and delete records using this interface.

## Admin panel
### Registering models
In Django, you can register your models with the admin site to make it easy to create, update, and delete records from your database via the admin interface.

## Response Codes
Django views return HTTP response codes to indicate the status of the request. Common codes include 200 (OK), 404 (Not Found), and 500 (Internal Server Error).

## Templates
Django uses a template system to generate dynamic HTML responses. You can use the Django template language to create templates that can include variables, tags, and filters.
