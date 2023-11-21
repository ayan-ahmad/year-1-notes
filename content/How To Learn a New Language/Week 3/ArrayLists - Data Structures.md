## Definition
An Array List is a dynamically sized version of [[Arrays - Data Structures]] implemented in Java.
## Sizes
**Capacity:** Size of the array
**Size:** Number of items in the array
## Syntax
### Initialise
```java
ArrayList<String> list = new ArrayList<>(); //implicit, set to 10 by default
ArrayList<String> list = new ArrayList<>(50); //explicit, set to 50
```
### Manipulating items
```java
list.add("Hello"); // Inserts at end
list.add(1, "World"); // Will shift other values and insert value
list.set(1, "World"); // Set item at index with value

list.get(0); // Get value at index 0
list.remove(1) // Removes item at index 1
list.remove("World") // Returns True or False
```

## Iterating
```java
for (int i = 0; i < list.size(); i++) {
	String s = list.get(i);
	System.out.print(s + " ");
} 

for (String s : list){
	System.out.print(s + " ");
}
```