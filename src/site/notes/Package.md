---
{"dg-publish":true,"permalink":"/package/"}
---

> From [Oracle's Java documentation](https://docs.oracle.com/javase/tutorial/java/package/packages.html), "A **package** is a grouping of related types providing access protection and name space management. Note that *types* refers to classes, interfaces, enumerations, and annotation types. Enumerations and annotation types are special kinds of classes and interfaces, respectively, so _types_ are often referred to in this lesson simply as _classes and interfaces_".

All files within a package must declare a package statement in the 1st line (`package farm`). Not doing so results in an "unnamed package" (not that it's bad or anything, just not sustainable for large volumes of code).

In order to use code apart of a `public` package outside of that package, you can refer to it by it's *Fully Qualified Name* (FQN) when needed
```java
farm.Dog doggo = new farm.Dog();
``` 

If the above becomes too repetitive, simply import the package at the start of the file. Because the FQN is referred above, you can use it's short name.  
```java
import farm.Dog; 

public static void main(String args[]) {
	Dog doggo = new Dog(); 
}
``` 
🤩 Fun Fact: java automatically performs a wildcard import of  `java.lang.*` so that we can use other classes by simple names (ie `java.lang.String` or `java.lang.System`). 

Can't stop the fun and want the whole package (you want multiple files from the same package)? So then do it! Be aware that only classes under the package will be important but not sub-packages (packages in a package). 
```java
import farm.*; // assuming it contains farm.Dog.java, farm.Cow.java, and farm.equipment.tractor.java

public static void main(String args[]) {
	Dog doggo = new Dog(); 
	Cow mooers = new Cow(); 
	// subpackages not imported tho! 
	farm.equipment.Tractor bigGuy = new farm.equipment.Tractor() 
}
```
