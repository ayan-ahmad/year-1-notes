## Definition
Interfaces are [[Pillars - OOP#Abstraction|abstract]] definitions of what a class (that implements the interface) should contain.
You can implement multiple interfaces.

Interfaces can only contain: constants, method signatures and static methods.
> [!tldr]- What are constants, method signature or static method
> ### Constants
> Constants are values that stay the same and are defined with the keyword `final` in Java
> 
> ### Method Signature
> A Method Signature is the name, input and output of a method. The below is an example:
> ```java
> int setGear(int gear)
> ```
> ### Static Methods
> Static methods are methods that start with the `static` keyword and can be run without initialising the class (see [[Class Concepts - OOP#Class Variables]])

e.g. we can have an interface for a `ManualCar` where we can have a `Fiat500` class that implements this. The `ManualCar` interface can require the class to have `changeGear` `isHandBrakeOn` `indicate` `accelerate` as these are functions that it should carry out but we don't specify how as each engine of a `ManualCar` will function differently.

## Implementation
To create an interface we use the `interface` keyword instead of `class`.

Worker.java
```java
package business;  
  
public interface Worker {  
    void doWork();  
    int getPay();
    void talkToCollegue(Worker worker);
}
```
Developer.java
```java
package business;

public class Developer implements Worker {
	@Override // You do not NEED this but it will throw errors and is very useful
	public void doWork(){
		System.out.println("Type typity type");
	}

	@Override
	public int getPay(){
		return 100000;
	}

	@Override
	public void talkToCollegue(Worker worker){
		if(worker.getPay() < 100000){
			System.out.println("Goodbye!")
		} else {
			System.out.println("Hello!")
		}
	}
}
```
HumanResources.java
```java
package business;

public class HumanResources implements Worker {
	@Override // You do not NEED this but it will throw errors and is very useful
	public void doWork(){
		System.out.println("Chit chitty chat");
	}

	@Override
	public int getPay(){
		return 99999;
	}

	@Override
	public void talkToCollegue(Worker worker){
		System.out.println("Hello!")
	}
}
```