## What are Enums
Enums are a set of predefined constants sort of like restricted choice for developers in the form of a variable. This allows you to keep your code humanised but not use ambiguous strings. You can make one for `GameState` which can be `WAITING`, `STARTING`, `IN_PROGRESS`, `GAME_OVER`, etc.
## Enum Defaults
|Method|Description|
|-----|------|
|values()|Provides all the enums|
|valueOf()|Turns strings into an enum|
|compareTo()|Preforms regular compareTo|
|equals()|Checks if 2 enums are equal to one another|
|toString()|Provides human readable String|
|name()|Gets the string value of the enum|
|ordinal()|Gets the position of the enum|
## Implementation
### Basic Implementation
Below is what a basic enum looks like:
```java
public enum GameState{
	WAIT,
	START,
	IN_PROGRESS,
	GAME_OVER
}
```
We can use this like a restricted choice by setting a variable to it, this variable can only possess these 4 values.

Here is what an implementation could look like:
```java
public class Game {
    private GameState state;

    public Game() {
        this.state = GameState.WAIT;
    }

    public void start() {
        if (this.state == GameState.WAIT) {
            this.state = GameState.START;
        } else {
            System.out.println("Cannot start game from current state: " + this.state);
        }
    }

    public void end() {
        if (this.state == GameState.IN_PROGRESS) {
            this.state = GameState.GAME_OVER;
        } else {
            System.out.println("Cannot end game from current state: " + this.state);
        }
    }

    public GameState getState() {
        return this.state;
    }
}

```
### Simple Value
Enums can also be associated to a value, this value must be declared in the constructor, in this example the value is suitName and is defined by putting `(VALUE)` beside the enum.
```java
public enum Suit {  
    CLUBS("Clubs"),  
    DIAMOND("Diamond"),  
    SPADES("Spades"),  
    HEARTS("Hearts");  
  
    private String suitName;  
  
    Suit(String suitName){  
        this.suitName = suitName;  
    }  
  
    public String getSuitName() {  
        return suitName;  
    }  
}
```
You can preform `Suit.getSuitName();` whenever you have an enum.

### Advanced Value
You can add any type for the associated value, in this example we have a pair and it can be accessed the same way with `Rank.getRankPair().getRank();` for example:
```java
class RankPair {  
    private String name;  
    private int rank;  
  
    public RankPair(String name, int rank) {  
        this.name = name;  
        this.rank = rank;  
    }  
  
    public String getName() {  
        return name;  
    }  
  
    public void setName(String name) {  
        this.name = name;  
    }  
  
    public int getRank() {  
        return rank;  
    }  
  
    public void setRank(int rank) {  
        this.rank = rank;  
    }  
}  
```

``` java
public enum Rank {  
    ACE(new RankPair("Ace", 1)),  
    DUECE(new RankPair("Duece", 2)),  
    THREE(new RankPair("Three", 3)),  
    FOUR(new RankPair("Four", 4)),  
    FIVE(new RankPair("Five", 5)),  
    SIX(new RankPair("Six", 6)),  
    SEVEN(new RankPair("Seven", 7)),  
    EIGHT(new RankPair("Eight", 8)),  
    NINE(new RankPair("Nine", 9)),  
    TEN(new RankPair("Ten", 10)),  
    JACK(new RankPair("Jack", 11)),  
    QUEEN(new RankPair("Queen", 12)),  
    KING(new RankPair("King", 13));  
  
    private RankPair rankPair;  
  
    Rank(RankPair rankPair) {  
        this.rankPair = rankPair;  
    }  
  
    public RankPair getRankPair() {  
        return rankPair;  
    }  
}
```
