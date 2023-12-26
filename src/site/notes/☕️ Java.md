---
{"dg-publish":true,"permalink":"/java/"}
---

Java is also a [[OOP\|OOP]] [[Programming Languages\|Programming Languages]]. The Java compiler translates the [[Programs\|program]] into *byte-code* for the Java Virtual Machine (JVM) -- Write once, run everywhere. 
# Coding Conventions
## Naming Conventions 
1. Class Names - `SlinkyDog` 
	- descriptive nouns 
	- always starts with caps, new words caps
3. Method Name - `fly()`, `goToTheStore()` 
	- verbs 
	- always starts with lower, new words caps 
4. Accessor Methods - `getToyOwnerName()`
	- gets info from instance variables 
	- always starts with `get` 
5. Mutator Methods - `setToyOwnerName(String ownerName)`
	- changes value of some attibute 
	- always starts with `set`
6. Instance / Local Variables - `_numGreenArmyMen`, `numToys`
	- store state information about object 
	- always starts with lower, new words caps 
	- can use simple (ie i / j or x / y) for loops, coordinates
7. Constants - `DORYS_IQ`
	- declared with static final 
	- nouns, all caps
8. Importing Classes - `import course.prj.LiteBrite.LiteBox`
	- import each class you're using rather than the whole package (not `.*` basically) 
## Spacing Convention 
1. Indentation 
	- nested code indented 4 spaces from prev line 
2. Braces 
	- add a space, but opens same line as name 
	- close is aligned with open 
3. Line Limits 
	- no more than 80 characters (otherwise break it up) 
		- Operator Wrapping 
```java
		int x = getSomeNum()
		+ getSomeNum() 
		+ getSomeNum()
		+ getSomeNum(); 
```
	- Exceptions: import statements 
4. Skipping Lines 
	- between methods and logical chunks to chunk code 
5. Private Classes 
	- declared at the bottom of containing class 
## Internal Documentation 
1. One line Comment - `// hello`
2. Multiline Comment - `/* ... */`
3. Header Comment - `/** ... */`
	  ❌ `this method adds a graphic`
	  ✅ `this method adds an object which implements the ShapeInterface to the GraphicsCollection. This will cause the shape to be...`
4. Inline Comments - `// me again`
	- explain enough, but not excessive 
## Equality 
1. Reference equality
	- checks if 2 objects occupy same memory location (aka `==`); lowkey not gonna use, except for if an object is `null`
	- REMEMBER, [[primitive data\|Primitive Data types]] DO NOT extend the `object` class; must use reference equality, NOT value equality
2. Value equality 
	- checks if 2 objects are equal based on user's use case / design (aka `.equals()` ), unless overiden 
## String Literals 
the process of creating a string; 
- every time string is created, it created literals / constants stored in a string pool for fast access
```java
String literal = "Bruh"; 
String object = new String("Bruh"); 

// Using == operator 
literal == object;                 // false 
literal == "Bruh";                 // true
"Bruh" == "Bruh";                  // true
object = "Bruh";                   // false 
object == new String("Bruh");      // false

// Using .equals() 
literal.equals(object);            // true
object.equals(literal);            // true 
literal.equals("Bruh");            // true 
object.equals("Bruh");             // true 
"Bruh".equals("Bruh");             // true 
"Bruh".equals(new String("Bruh")); // true
```
## [[enumeration\|enumeration]]
# Libraries
In the Java Runtime Environment (JRE), there are various libraries built in that can be accessed in your code. Some, such as classes in `java.lang` like `Object`, `String`, or even basic data types (`int`, `boolean`). 

Here are some other examples: 
## Iterators 
A way to traverse through a data set
- implemented through an inner / private class
- implements the `Iterable` interface (`java.lang.package`) -> `iterator()` method 
- used by calling an instance of iterator to get each item 
Example for Singly-Linked List 
```java 
public class LinkedList<T> implements Iterable<T> { 
	// Other methods / variables not shown for brevity 
	@Override 
	public Iterator<T> iterator() {
		return new LinkedListIterator<T>(head); 
	} // iterator
	private static class LinkedListIterator<T> implements Iterator <T> {
		private Node<T> currentNode; 
		
		public LinkedListIterator(Node<T> startingNode) { 
		currentNode = startingNode; 
		} // LinkedListIterator
	} // LinkedListIterator<T>
} // LinkedList<T>
```

Source: [Oracle](https://docs.oracle.com/javase/8/docs/api/java/util/Iterator.html)
## Comparable
Comparable is an interface that when implemented, allows you to compare objects of the same class with various instances of that class. 

Source: Oracle
## [[Exception\|Exception]]

## [[Interfaces\|Interfaces]]

## Classes 
- [[Math Class\|Math Class]]
- [[Print Steam Class\|Print Steam Class]]
- [[String Class\|String Class]]
- [[Wrapper Class\|Wrapper Class]]

# Other Tools 
- [[Maven\|Maven]]
- [JavaFX] (you will never get a page...)