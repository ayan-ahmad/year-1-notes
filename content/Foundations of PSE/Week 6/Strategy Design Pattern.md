## Definition
Strategy Design Pattern allows for multiple ways for stuff to be changed for different behaviours

E.g. Say we want to alert users when something happens, people will have different preferences to be alerted.
We will have an interface called `MessageProviders`, this interface must include a method called `sendMessage`
Since we have an interface we can implement different providers with different providers.
We can iterate over ever user and send them a message easily for each provider.
The main purpose is that the core functionality will never change when you add on more.
### Written Example
```java
public interface MessageProviders{
	void sendMessage(String message, User user);
}
```

```java
public class Email implements MessageProviders{
	@Override
	public void sendMessage(String message, User user){
		System.out.println("Emailed: " + user.name)
	}
}
```

```java
public class SMS implements MessageProviders{
	@Override
	public void sendMessage(String message, User user){
		System.out.println("SMS: " + user.name)
	}
}
```

```java
public class User{
	public String name;
	public MessageProviders messageProviders;

	User(String name, MessageProviders messageProviders){
		this.name = name;
		this.messageProviders = messageProviders;
	}

	public static void main(String[] args) {
	    User user1 = new User("Derek", new SMS());
	    User user2 = new User("Matt", new Email());
	    User[] users;
	    users.add(user1);
	    users.add(user2);
	    // The below code is "core functionality" and it will never change with the more providers you add
	    for(User user : users){
		    user.messageProviders.sendMessage();
	    }
	}
}
```

