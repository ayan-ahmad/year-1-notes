## Definition
Arrays are like [[Lists - Data Structures]] in that they have multiple items, however arrays hold items of single [[Types]] and have a fixed length at definition.
## Initialising
### Default values
If an array is being initialised with integers the items will be set with a value `0`
### Dimensionality
When defining you can set the dimensions of an array
### Example
#### Default Values
```java
int[] values = new int[10];
System.out.println(values[0]); // 0
```
#### Dimensionality
```java
int arr = new int[10][10]
arr[0][0] = 1
System.out.println(arr[0][0]); // 1
```
## Iteration
```java
for (int i = 0; i < strings.length ; i++) {
	System.out.println(strings[i]);
}

for (String s : strings) {
	System.out.println(s);
}
```

```cs
foreach (string s in strings) {
	Console.WriteLine(s);
}
```
