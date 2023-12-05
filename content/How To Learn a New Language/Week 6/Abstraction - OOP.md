## Definition
An abstract class is like a mix between a normal [[Class Concepts - OOP|class]] mixed with an [[Interfaces - OOP|interface]].

Like a class:
- Allows implementation
- Allows declaration of all variables

Like an interface:
- Cannot be initialised
- You can define methods with and without implementation 

What's different:
- Use of the `abstract` keyword to require implementation
- Declare variables which are not static and final (interfaces cannot do this)
- A class can only extend one abstract class
### When to use what
- We use an abstract class when `x is y` (see [[UML]], you would use this for a `Fiat500` is a `Car`)
- We use an interface when `x is capable of doing y` (e.g. from [[Strategy Design Pattern]], the example of providers may be able to do more than just message, some may have call functions, `MessageProvider` is capable of `sendMessage`)
