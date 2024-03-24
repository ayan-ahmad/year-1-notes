## Error Handling
### 404
The 404 error occurs when the location requested does not exist.
This may occur if:
%%add code example%%
## Templates
Templates are a blueprint for your webpage. It provides a structure for your webpage whilst allowing for you to display different content dynamically.
%%add DJango Specific*%%
### The 4 Constructs of DTL
#### Variables
- Variables come from the context provided to the templates
- They are surrounded by `{{` and `}}`
	`I am {{name}} and I am {{age}} years olf!`
- With a context of `{'name': 'Ayan', 'Age': 17}`
	`I am Ayan and I am 17 years old`
- We can preform:
	- Dictionary lookup
	- Attribute lookup
	- List index lookup
	%%add code examples for each lookup%%
#### Tags
%%finish later%%
#### Filters
%%finish later%%
#### Comments
If we want to add comments which will not be rendered we can do this by surrounding the comment with `{#` and `#}` for a single line and %%find multi line%%
### Dynamic URLs
%%finish later%%
## Forms
### Implementation
%%finish later%%
### CSRF Token
%%finish later%%

## Population Scripts
