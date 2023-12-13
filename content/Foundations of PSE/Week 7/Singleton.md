## Definition
Singletons are classes which can only be instantiated once.
## Use Case
You would use this for something you only want one of. For example if you have a game
## Possible Problems
There can be issues if multiple threads call getInstance for the first time, a regular implementation is not [[#Thread Safe]]
## Thread Safe
If something is thread safe it means that it can be used in threads safely without causing any issues.
Here are some solutions:
- Create the singleton at start-up
- Make getInstance synchronous with the `synchronized` keyword (only 1 thread can work at a time)
## Implementation
```java
public class SomeSingleton{
	private static SomeSingleton instance;

	public static SomeSingleton getInstance(){
		if(instance == null){
			instance = new SomeSingleton();
		}
		return instance;
	}

	private SomeSingleton(){} // Note the constructor is PRIVATE
}
```

```java
public class ARandomClass{
	public SomeSingleton getASingletonFromAnotherClass(){
		return SomeSingleton.getInstance();
	}
	public ARandomClass(){}
}
```

```java
public class SomeClass{
	public static void main(String[] args){
		SomeSingleton someSingleton1 = SomeSingleton.getInstance();
		SomeSingleton someSingleton2 = new ARandomClass().getASingletonFromAnotherClass();
		// The above 2 reference the exact same initialised class
	}
}
```