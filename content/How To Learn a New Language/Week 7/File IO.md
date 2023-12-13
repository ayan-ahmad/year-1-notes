## Writing to a file
```java
import java.io.*;  
  
public class BufferedFileWriterIO {  
    public static void main(String[] args) {  
        String path = "some_file.txt";  
        try {  
            BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(path));  
            bufferedWriter.write("Hello \n World");  // Writes to file
            bufferedWriter.close();  
        } catch (IOException e) {  
            System.out.println("Could not access file");  
        }  
    }  
}
```
## Reading from a file
```java
import java.io.*;  
  
public class BufferedFileReaderIO {  
    public static void main(String[] args) {  
        String path = "some_file.txt";  
        try {  
            BufferedReader bufferedReader = new BufferedReader(new FileReader(path));  
			String line;  
			while((line = bufferedReader.readLine()) != null){  
			    System.out.println(line); // Prints every line
			}
            bufferedReader.close();  
        } catch (IOException e) {  
            System.out.println("Could not access file");  
        }  
    }  
}
```