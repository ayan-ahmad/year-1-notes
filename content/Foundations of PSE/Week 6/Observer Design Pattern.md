## Definition
The observer design pattern is a design pattern to provide a solution to consumption of real time data.

In this we have an observer which watches for updates from a specific subject. The subject will notify all the subscribers to the subject.
### Polling
Polling is an old version on retrieving 
### Pushing
When a subject makes a change and informs the subscribed observers this is called pushing
### Written Example
Here are simple interfaces for implementing both an observer and subject.

We have an application that takes in user inputs and announces them in different ways (for a simple example we just add a custom prefix)

Subject Interface
```java
public interface Subject {  
    void registerObserver(Observer observer);  
    void removeObserver(Observer observer);  
    void notifyObserver(String message);  
}
```

Observer Interface
```java
public interface Observer {  
    void update(String message);  
}
```

Subject Implementation
```java
import java.util.ArrayList;  
import java.util.List;  
import java.util.Scanner;  
  
public class UserMessages implements Subject {  
  
    private List<Observer> observers = new ArrayList<Observer>();  

	// This just takes user input and can be ignored!
    public void getUserInput(){  
        Scanner scanner = new Scanner(System.in);  
        while (true)  
            notifyObserver(scanner.nextLine());  
    }  
  
    @Override  
    public void registerObserver(Observer observer) {  
        observers.add(observer);  
    }  
  
    @Override  
    public void removeObserver(Observer observer) {  
        observers.remove(observer);  
    }  
  
    @Override  
    public void notifyObserver(String message) {  
        for (Observer observer : observers){  
            observer.update(message);  
        }  
    }  
}
```

Observer Implementation
```java
public class AnnounceMessages implements Observer {  
    private String prefix;  
  
    AnnounceMessages(String prefix){  
        this.prefix = prefix;  
    }  
  
    @Override  
    public void update(String message) {  
        System.out.println(prefix + ": " + message);  
    }  
  
    public static void main(String[] args) {  
        AnnounceMessages announceMessages1 = new AnnounceMessages("Announcement 1");  
        AnnounceMessages announceMessages2 = new AnnounceMessages("Announcement 2");  
        
        UserMessages userMessages = new UserMessages();  
        
        userMessages.registerObserver(announceMessages1);  
        userMessages.registerObserver(announceMessages2);  
        
        userMessages.getUserInput();  
    }  
}
```