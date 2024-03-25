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
### Simple HTML
We can simply respond with a HTML element in the `HTMLResponse` like so:
```python
from django.http import HttpResponse

def index(request):
	return HttpResponse("<h1>Hello, world.</h1><p>You're at the index page</p>")
```
## Data sources
### Models
Models in Django are used to represent data sources. A model is a Python class that inherits from the `django.db.models.Model` class, and represents a database table. Django uses SQLite by default.
### Creating Models
To create a model, you define a class in `models.py` and specify the fields for the model.
```python
# models.py

from django.db import models
from django.utils import timezone

class Post(models.Model):
    title = models.CharField(max_length=64)
    content = models.TextField()
    created_date = models.DateTimeField(default=timezone.now)
    published_date = models.DateTimeField(blank=True, null=True)

    def __str__(self):
        return self.title
```
## Admin panel
### Registering models
In Django, you can register your models in `admin.py` to show on the website.
```python
from django.contrib import admin
from .models import Post

admin.site.register(Post)
```
## Response Codes
Django views return HTTP response codes to indicate the status of the request. Common codes include 200 (OK), 404 (Not Found), and 500 (Internal Server Error).
## URL Mappings
To create more complex mappings we can do:
```python
# urls.py

from django.urls import path
from . import views

urlpatterns = [
    path('', views.index, name='index'),  # Map the root URL to the index view
    path('<int:post_id>/', views.detail, name='detail'),  # Map post detail URL with post ID
    path('<int:post_id>/edit/', views.edit, name='edit'),  # Map post edit URL with post ID
    path('create/', views.create, name='create'),  # Map post creation URL
]
```
## Templates
Here is an example of a template, we will talk about this more in [[Templates and URLs]]:
```html
<!-- templates/index.html -->

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Blog</title>
</head>
<body>
    <h1>Welcome to My Blog</h1>
    <ul>
        {% for post in posts %}
            <li>
                <h2>{{ post.title }}</h2>
                <p>{{ post.content }}</p>
                <p>Published by {{ post.author }} on {{ post.published_date }}</p>
            </li>
        {% endfor %}
    </ul>
</body>
</html>

```

