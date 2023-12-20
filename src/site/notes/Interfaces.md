---
{"dg-publish":true,"permalink":"/interfaces/"}
---

A special type of class that lists a group of methods that describes a set of actions that a broad range of objects can perform (but not necessarily how to do so). Other classes implement this interface and bind themselves to implement the functionality of the interface (finish the body). Interfaces are also considered as a [[Reference data types\|reference data type]] because objects are simply instances from a specific class implementing the interface.  

```java
// an example of a simple interface
interface Animal {
  public static int num = 1; // interface variable (constant and static)

  public void animalSound(); // interface method (does not have a body)
  public void run(); // interface method (does not have a body)
}
```

One more time for those in the back: the interface is a broad category of a specific type of object, creating a basic skeleton of methods, but freedom to do so. Think of animal classification, vehicles, or anything else your heart desires. The key here is a flexible implementation of the requirements. And with this flexibility, it's important to write the proper [[API#Javadoc Comments\|documentation]] so that other users know how to properly implement the class. 

Taking a close look at our interface, there are two specific things to note: 
1. <u>Abstract Methods</u> are non-static methods without an implementation (aka the body)
	- `public void style()` for example
2. [[constants\|constants]] are unchanging variables (because if we have more than one class implementing the interface, we would have a conflicting variable). 

As a side note, interfaces can also implement [[Static Methods\|static methods]] and <u>Default Methods</u>. To the internet if you're interested. 

Now, let's take a look at a class that's implementing an interface. 
```java 
public class Dog implements Animal {
	String name; 
	String breed; 

	public void animalSound() {
		System.out.println("woof"); 
	}
		
	public void run() {
		System.out.println(this.name + " is running!"); 
	}
	
}
```

Here, `Dog` is the implementing class that has signed the `Animal` contract. Without implementing the abstract methods, the class won't compile. If we wanted to create a `Cat`, we would simply have `Cat` implement `Animal`. That's where interfaces become powerful! 