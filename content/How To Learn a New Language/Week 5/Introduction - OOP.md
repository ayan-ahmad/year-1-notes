## Object Oriented Programming
Object Oriented Programming (OOP), has 4 pillars: abstraction, encapsulation, inheritance, polymorphism
### Classes
Classes are blueprints, classes prevent us from repeating lines of code.
e.g.: A `human` class that takes arguments `name, gender, age, etc.`, this class will contain common humanly functions such as: `eating, sleeping, etc.`, you can initialise any human class with anyone and keep the same functions on the person:
```java
public class Human {

	public String name;
	public String gender;
	private int age;

	public Human(String name, String gender, int age) { // This is a constructor
		this.name = name;
		this.gender = gender;
		this.age = age;
	}

	public void introduce() {
		System.out.println("Hello, my name is: " + name);
	}

	public int getAge() {
		return age;
	}
}
```

```java
public class World {
	public static void main(String[] args) {
		Human lordFarquaad = new Human("Lord Farquaad", "Male", 571);
		lordFarquaad.introduce(); // Prints "Hello, my name is: Lord Farquaad"
		System.out.println("I am : " + lordFarquaad.age); // This will throw an error
		System.out.println("I am : " + lordFarquaad.getAge()); // This will print "I am: 571"
	}
}
```
## Abstraction
Abstraction is the simplification of an object and provides a high-level interface for other objects which interact with it:
This includes:
- Making high-level methods public and accessible by other objects
  **With Abstraction**
  1. Get ready for university
  **Without Abstraction**
  1. Wake up
  2. Get out of bed
  3. ...
  4. Leave for university
## Encapsulation
Encapsulation is removing access to parts of your object if they are not required outside of the object.
e.g.: Say we have a `Microwave` object and you want to heat up your food for 1min. As a human I do not need to be able to access the voltage and to change it, the only thing I need to be able to do is put the food in the microwave and turn it on for 1min. So we should make the voltage property private.
## Inheritance
Inheritance reduces the reuse of code by allowing methods from another class (it's parent class) to be added to your current class (child class).
e.g.: the `Human` class will have methods and properties such as `name, speakEnglish, useComputer` but will inherit common animal methods and properties from the `Animal` class such as `isAlive, eat, sleep, move, species`
In Java we use the keyword `extends` in our class definition like:
```java
public class Human extends Animal{}
```
## Polymorphism
Polymorphism allows a single interface to be used for more general purposes.
Take the `System.out.println` function as an example, you can call it empty to return an empty new line like `System.out.println()` and you can also print strings or integers `System.out.println("Hello World!")` or `System.out.println(256)`