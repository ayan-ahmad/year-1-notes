## Error Handling
### 404
The 404 error occurs when the location requested does not exist.
This may occur if:
- The location has been moved
- The file never existed
```python
def post(request, post_id):
	try:
		post = Post.objects.get(pk=post_id)
	except Post.DoesNotExist:
		raise Http404("Post does not exist")
		
	return render(request, "blog/post.html", {"post": post})
```
## Templates
Templates are a blueprint for your webpage. It provides a structure for your webpage whilst allowing for you to display different content dynamically.

In Django, templates are written using Django Template Language (DTL), which allows you to insert dynamic data into your HTML templates.
### The 4 Constructs of DTL
#### Variables
- Variables come from the context provided to the templates
- They are surrounded by `{{` and `}}`
	`I am {{name}} and I am {{age}} years olf!`
- With a context of `{'name': 'Ayan', 'Age': 17}`
	`I am Ayan and I am 17 years old`
- We can preform:
	- Dictionary lookup
		- `{{ my_dict.key }}`
	- Attribute lookup
		- `{{ my_object.attribute }}`
	- List index lookup 
		- `{{ my_list.0 }}`
#### Tags
Tags are used for control flow, such as loops and conditionals, and for loading external content.
```
{% if condition %}
    Display this text if the condition is True.
{% endif %}
```
#### Filters
Filters modify the output of variables. They can be used to format numbers, strings, dates, and more.
```
{{ value|filter }}
```
#### Comments
If we want to add comments which will not be rendered we can do this by surrounding the comment with `{#` and `#}` for a single line and for multi line:
```
{% comment "Optional note" %}
	<p>Commented out text with {{ create_date|date:"c" }}</p>
{% endcomment %}
```
### Namespacing URL names
In big Django projects there may be many apps and several may have detail views, therefore you can differentiate between the apps using namespaces.

Add the `app_name` variable to `urls.py` in your app. You can now use it for dynamic links
```html
<!-- Old -->
<li><a href="{% url 'post' post.id %}">{{ question.title }}</a></li>

<!-- New -->
<li><a href="{% url ‘blog:post' post.id %}">{{ question.title }}</a></li>
```
## Forms
### Implementation
```html
<form action="{% url 'create_post' %}" method="post">
    {% csrf_token %}
    <fieldset>
        <legend><h1>Create New Blog Post</h1></legend>
        <label for="title">Title:</label><br>
        <input type="text" id="title" name="title"><br><br>
        <label for="content">Content:</label><br>
        <textarea id="content" name="content"></textarea><br>
    </fieldset>
    <input type="submit" value="Create Post">
</form>
```
### CSRF Token
Cross-site request forgery (CSRF), also known as XSRF or Sea Surf, is a type of web security vulnerability that tricks an authenticated user into unknowingly performing an action on a website they're logged into.

Since the user is already logged into the vulnerable website, their browser automatically sends their cookies and other authentication information along with the attacker's forged request.

The `{% csrf_token %}`prevents this.

%%## Population Scripts
finish later%%
