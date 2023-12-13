## What is an exception
An exception is when something unexpected happens like when an error prompt shows if you do something wrong in an app. Unhandled exceptions will cause crashes.
## Error Handling
To control errors we use `try/catch blocks`. This will look for specific exceptions and catch them before they cause any harm like a crash. Inside the catch block you can provide warnings to your users. You may also add the optional `finally` block to run code after it has either ran or failed
## Implementation
```java
public class Example {
    public static void main(String[] args) {
        int[] arr = {1, 2, 3};
        try {
            System.out.println(arr[3]);
        } catch (ArrayIndexOutOfBoundsException e) {
	        // You can make the above just 'Exception' and it will catch all of them but it is generally bad practice
            System.out.println("Array index out of bounds!");
        } finally {
            System.out.println("This code will always run.");
        }
    }
}
```