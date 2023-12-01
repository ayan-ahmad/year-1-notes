## Overriding
Overriding is essentially replacing an inherited property with a new value.

Say the class `Animal` has a `toString()` function which returns `Species: species, Breed?: breed, Age: age`

Now say we extend `Animal` and make the `Human` class. We want to make `toString()` behave differently to show name and job. To do this we use overriding!
## Overloading
Overloading is allowing multiple different types of data being allowed to pass into a function.
```java
public static int addOne(String str){  
    System.out.println("String inputted");  
    return Integer.valueOf(str) + 1;  
}  
  
public static int addOne(int num){  
    System.out.println("Integer inputted");  
    return ++num;  
}  
  
public static void main(String[] args) {  
    System.out.println(addOne("100"));  // String inputted 101
    System.out.println(addOne(100));  // Integer inputted 101
}
```
## Final Keyword
- Prevents method overriding when inherited
- If put on a class it will prevent it from being inherited