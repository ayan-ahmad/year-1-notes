## Local
Locally scoped variables can only be accessed on the same scope
## Global
Globally scope variables can be accessed anywhere in the program

To edit data in a global variable in a local scope in python use the global keyword:
```python
x = 15

def change():
    # using a global keyword
    global x

    # increment value of a by 5
    x = x + 5
    print("Value of x inside a function :", x)

change()

print("Value of x outside a function :", x)
```
## Shadow
Variable shadowing occurs when a local variable has the same name as a global variable overwriting the access within the local scope