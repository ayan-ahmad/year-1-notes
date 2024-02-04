## Definition
The Iterator Design Pattern provides a way to access elements of an aggregated object sequentially with out exposing its underlying representation
## Use Case
- Private list or array
- You want to avoid other classes amending your list or array
## Possible Problems
1. **Limited Flexibility:** May not support complex iterations or alternative traversal orders.
2. **Increased Complexity:** Introducing additional classes may add complexity for simpler scenarios.
3. **Performance Overhead:** Depending on implementation, there might be a slight performance cost.
4. **Synchronization Issues:** Changes to the hand during iteration could cause synchronization problems.
5. **Limited Operation Support:** Some Iterator variations may only support basic operations.
## Implementation
To implement we first need to create the iterator interface:
```java
public interface Iterator {
    boolean hasNext();
    Card next();
}
```
Now we need to implement this interface:
```java
public class Hand implements Iterator {
    private List<Card> cards;
    private int position;

    public boolean hasNext(){
	    return position < cards.size();
    }

	public Card next(){
		Card card = cards.get(position);
		position++;
		return card;
	}
}

```