## Definition
The state design pattern is a common design pattern for dealing with states that changes how a class acts.
## Use Case
The state design pattern is used when internal state that changes will alter the behaviour of a class.

All the logic is separate from the core logic.
## Implementation
For the implementation we must have an interface for a state.
Each state will be it's own class, in this class we will have the different behaviour for this specific state.
The core functionality should stay the same
```java
public class Shop{  
    private ShopState shopState = new ClosedShop(this);  
  
    public ShopState getShopState(){  
        return this.shopState;  
    }  
  
    public void setShopState(ShopState shopState){  
        this.shopState = shopState;  
    }  
  
    public void enterShop(){  
        shopState.enterShop();  
    }  
  
    public static void main(String[] args){  
        Shop shop = new Shop();  
        shop.enterShop(); // You May NOT Enter
        shop.enterShop(); // You May NOT Enter
        shop.enterShop(); // You May NOT Enter
        shop.setShopState(new OpenShop(shop));  
        shop.enterShop(); // You May Enter
        shop.enterShop(); // You May Enter
    }  
}
```

```java
public interface ShopState{
	public void nextState();
	public void enterShop();
}
```

```java
public class OpenShop implements ShopState{  
    private Shop shop;  
  
    public OpenShop(Shop shop){  
        this.shop = shop;  
    }  
  
    @Override  
    public void nextState(){  
        shop.setShopState(new ClosedShop(shop));  
    }  
  
    @Override  
    public void enterShop(){  
        System.out.println("You May Enter");  
    }  
}
```

```java
public class ClosedShop implements ShopState{  
    private Shop shop;  
  
    public ClosedShop(Shop shop){  
        this.shop = shop;  
    }  
  
    @Override  
    public void nextState(){  
        shop.setShopState(new OpenShop(shop));  
    }  
  
    @Override  
    public void enterShop(){  
        System.out.println("You May NOT Enter");  
    }  
}
```