## Variable types
### Class Variables
Class variables are variables that are shared across all instances of a class.
e.g.: A version variable that is held in the program would be a class variable as it should be the same for every instance of the class

Java
```java
public class Variables {  
    public static int version = 1;  
  
    public Variables() {}  
  
    public static void main(String[] args) {  
        Variables var1 = new Variables();  
        Variables var2 = new Variables();  
  
        System.out.println("var 1 version: " + var1.version);  //1
        System.out.println("var 2 version: " + var2.version);  //1
        System.out.println("variable class: " + Variables.version); //1 
  
        Variables.version += 1;  
  
        System.out.println("var 1 version: " + var1.version);  //2
        System.out.println("var 2 version: " + var2.version);  //2
        System.out.println("variable class: " + Variables.version);  //2
    }  
}
```

Python
```python
class Variables:
	version = 1

var1 = Variables()
var2 = Variables()

print(var1.version) #1
print(var2.version) #1
print(Variables.version) #1

Variables.version += 1

print(var1.version) #2
print(var2.version) #2
print(Variables.version) #2
```

> [!NOTE] Note
> An instance is a version of the class which is initialised with the `new` keyword in most languages

Python (static method)
### Instance
Instance variables are variables that are unique for each instance of a class

Java
```java
public class Counter {  
    public int total = 0;  
  
    public Counter() {}  
  
    public static void main(String[] args) {  
        Counter counter1 = new Counter();  
        Counter counter2 = new Counter();  
        counter1.count().count().count();  
        counter2.count().count().count().count().count();  
        System.out.println("Counter1 total: " + counter1.total);  //Counter1 total: 3
        System.out.println("Counter2 total: " +counter2.total);  //Counter2 total: 5
        //Note: you can't do Counter.total here as it is an instance variable
    }  
  
    public Counter count(){  
        total++;  
        return this;  
    }  
}
```

Python
```python
class Counter:
	def __init__(self):
		self.total = 0

	def count(self):
		self.total+=1
		
counter1 = Counter()
counter2 = Counter()
counter1.count()
print(counter1.total) #1
print(counter2.total) #0
```
### Final
The final keyword makes a variable unable to be changed/edited. It is usually used alongside the static keyword.

### Local
Refer to [[Scope]]
### Global
Refer to [[Scope]]
