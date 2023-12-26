---
{"dg-publish":true,"permalink":"/classes/"}
---

A class is essentially a container for a bunch of instructions that are logically related. It allows you to group together different aspects of a process or concept in a structured way, making it easier to understand and manage. It can be particularly useful when you are reusing code to create multiple instances of the same piece of code (aka objects). 

Here is an example of a simple class in Java called "Dog":
```java 
public class Dog {
    // instance variables
    private String name;
    private int age;
    
    // constructor
    public Dog(String name, int age) {
        this.name = name; // Instance Variable 
        this.age = age;   // Instance Variable
    }
    
    // method 1: getter
    public String getName() {
        return name;
    }
	
	// method 2: getter 
    public int getAge() {
        return age;
    }

	// method 3
    public void celebrateBirthday() {
        age++;
        System.out.println("Happy birthday, " + name + "! You are " + age + " years old.");
    }
}
```

In this example, the class "Person" has the following key features:
- **Instance Variables**: The class defines two private instance variables, "name" (of type `String`) and "age" (of type `int`), which represent the properties or attributes of a person.
- **Constructor**: The class has a constructor that takes in parameters (name and age) to initialize the instance variables when a new object of the class is created.
- **Methods**: The class provides various methods to interact with its data. There are getter methods, such as `getName()` and `getAge()`, that allow access to the private instance variables. Additionally, there is a method called `celebrateBirthday()` that increments the age by 1 and prints a birthday message to the console.

In order to run a class(es), you will have a specific main method (very familiar...) that will initialize other class(es) that you want. Note that depending on how structured your code is, usually a separate main class (also called a driver class) is used, but simple a method will compile: 
```java 
public static void main(String[] args) {
    // Creating an instance of the Dog class with a Constructor! 
    Dog myDog = new Dog("Buddy", 3); 

	// Accessing and printing initial values
	System.out.println("Initial values:");
	System.out.println("Name: " + myDog.getName()); // prints "Name: Buddy" 
	System.out.println("Age: " + myDog.getAge()); // prints "Age: 3"

	// Calling the celebrateBirthday method
	myDog.celebrateBirthday(); // prints "Happy Birthday Buddy! You are 4 years old"

	// Accessing and printing updated values
	System.out.println("\nAfter celebrating birthday:");
	System.out.println("Name: " + myDog.getName()); // prints "Name: Buddy" 
	System.out.println("Age: " + myDog.getAge());   // prints "Age: 4"
    }
```
To recap, in this example, we create a `Dog` ***object*** called `myDog`, set its initial values using the constructor, and then call the `celebrateBirthday` method to update the age and print a birthday message. Finally, we print the updated values of the dog's name and age.

These features exemplify how a class can encapsulate data and behavior, allowing for data manipulation and providing controlled access to its properties. Additionally, they demonstrate how a class provides a blueprint to create objects that possess the defined attributes and behaviors.

With more sophisticated classes, programers utilize various diagraming tools, such as [[UML Class Diagrams\|UML Class Diagrams]].

# Instance Variables 
An instance variable in programming refers to a variable that is declared within a class but outside any method or constructor. It holds data that is unique to each instance or object of a class. Unlike local variables, which are local to a specific method or block, instance variables are accessible throughout the entire class.

While you can refer to the variable itself in the class, it's more common to use the keyword `this` to refer to instance variables for clarity (especially when the instance variable and other variables have the same name). 

"Getter" and "Setter" methods are another aspect of instance variables. They allow you to read the values of and modify the values respectively (say if they are private variables) within another class or method. 
# Methods 
A **method** (also known as a function or a procedure in other programing languages) is a block of code that performs a specific task or set of tasks defined within a class. Methods are used to organize code into reusable and modular units, making it easier to manage and understand the logic of a program while also reducing redundancy. 

Here's a basic structure of a method in Java:
```java 
returnType methodName(parameter1Type parameter1, parameter2Type parameter2, ...) {
    // Method body
    // Code to perform a specific task
    // Return statement if applicable
}
```
- **return type:** specifies the type of value that the method will return. Use `void` if the method does not return any value
- **method name:** name of the method, which is used to call and execute the code in the method
- **parameters:** variables that are received when it is called, used to pass information into the method
	- note: the method name and parameter together is refered to as the method signature

Below we explore general categories of methods: 
## Constructors 
**Constructors** are special methods that are called when an *instance* of a [[Classes\|class]] is created using the keyword `new`. They initialize the object and allocate memory for its variables. 
- Constructors do not have a return type, not even `void`. Instead, they implicitly return a reference to the newly created object. 
- Constructors can have parameters, allowing for initialization of object properties with specific values. 
- Defining multiple constructors with different parameters can provide flexibility when creating objects. If no parameters are specified, a default constructor with no arguments is automatically generated. 
- Every constructor ***must*** have the same name as the class. Constructors are essential in [[OOP\|object-oriented programming]] to ensure proper initialization and setup of objects when they are created.

Above, we see that the constructor with parameters takes in a `name` and an `age` and initializes the respective instance variables `name` and `age` using this. By using this, we differentiate between the parameter variables and the instance variables with the same name.
## Void Methods 
A void method is simply one that doesn't return anything back. 
```java
void plantSeeds(int numberOfSeeds) {
    System.out.println("Planting " + numberOfSeeds + " seeds in the soil.");
    // Code to plant seeds
}
```

## Static Methods 
A **static method** is one that is associated with a class as a *whole*, rather than with a specific instance of the class. This implies that invoking a static method is done on the class directly, without the need to create an instance of the class. The declaration of static methods involves the use of the keyword `static`.
```java
static void farmStatistics(int totalCrops, int totalAnimals) {
    System.out.println("Farm Statistics:");
    System.out.println("Total crops: " + totalCrops);
    System.out.println("Total animals: " + totalAnimals);
}
```

Some key ideas here as these can be a bit tricky at first: 
- Static Methods can *only* access static variables of a class -- they cant access any instance variables or methods within a class, unless they create an instance of that class  
- They are associated with the class as a whole, NOT an instance of the class

### Static Variables 
**Static variables** belong to the [[Classes\|class]] rather than instances (objects!) of the class and thus are shared among all objects of that class. These variables are declared using the `static` keyword, making them accessible ***without*** creating an instance of the class. Their importance lies in their ability to store data that is common to all instances of the class, avoiding redundant storage for each instance.

Note: variables declared with `static final` are [[constants\|constants]]!
Also Note: static variables cannot use the keyword `this` 

```java
public class Animals {
    // Static variable to store the total number of animals on the farm
    private static int totalAnimals = 0;

    // Constructor increments the totalAnimals count when a new animal is added to the farm
    public Animals() {
        totalAnimals++;
    }

    // Static method to get the total number of animals on the farm
    public static int getTotalAnimals() {
        return totalAnimals;
    }
}
```
The `totalAnimals` static variable is shared among all instances of the `Animals` class. Each time a new animal is added to the farm (an instance of `Animals` is created), the static variable is incremented.
## Overloaded Methods
An **overloaded method** is simply where there are several methods with the same name, but different parameters in a class. Because we providing multiple ways to invoke a particular functionality, we can create more versatile and flexible code. 

Feeding animals can be tricky, but rather than having so many animal feeding methods, we can simply have "one": 
```java
public class Feeding {
    // Method for feeding a generic animal
    public void feedAnimal(String animal) {
        System.out.println("Feeding " + animal + " with general feed.");
    }

    // Overloaded method for feeding cows with specific feed
    public void feedAnimal(String animal, String feedType) {
        if (animal.equalsIgnoreCase("cow")) {
            System.out.println("Feeding the cow with " + feedType + " feed.");
        } else {
            System.out.println("Feeding " + animal + " with general feed.");
        }
    }

    // Overloaded method for feeding chickens with specific feed
    public void feedAnimal(int numberOfChickens, String feedType) {
        System.out.println("Feeding " + numberOfChickens + " chickens with " + feedType + " feed.");
    }
}

```
# Visibility Modifiers  
**Visibility modifiers**, also referred to as *access modifiers*, are important in regulating the accessibility of classes, methods, and fields (such as variables). Here are the four main visibility modifiers in Java along with examples

1. **Public:** The `public` modifier allows members to be accessed from any class, irrespective of the [[Package\|package]]. 
```java
public class MyFarm {
    public int numApplesPicked;
    /* other fields */
    
    public void collectApples() {
        // code here
    }
    /* other methods */
}
```
In another class, you can create a `MyFarm` object and use the `collectApples()` method and modify the `numApplesPicked` variable for the object. 

2. **Private:** The `private` modifier restricts access to members only within the same class, making them invisible to other classes, even within the same package.
```java
public class MyCow {
    private int farmID;
    /* other fields */
    
    private void changefarmID() {
        // code here
    }
    /* other methods */
}
```
In another class, you can create a `MyCow` object, but you cannot change the `farmID` or access the `changefarmID()` method to modify a `MyCow` object's ID (in the real world, you wouldn't want people stealing your cows!). You can only access these two things from within the `MyCow` class. 

3. **Protected**: The `protected` modifier enables access within the same class, the same package, and by subclasses, even if they belong to a different package.
```java
public class MyDoggo {
    private String name;
    protected int animalsEncounterd; 
    /* other fields */
    protected void encounterFriend() {
        // code here
    }
    /* other methods */
}
```
Other classes within the same package as `MyDoggo` and its subclasses (regardless of their package) can access and modify the `animalsEncountered` field and call the `encounterFriend()` method.

4. **Default (Package-Private):** When no modifier is specified, the default visibility is package-private. Members with package-private visibility are accessible solely within the same package.
```java
package com.example.animals;

class AnimalFarm {
    private String farmName;
    int numberOfAnimals; // package-private visibility

    AnimalFarm(String name) {
        this.farmName = name;
        this.numberOfAnimals = 0;
    }

    void addAnimal() {
        numberOfAnimals++;
    }

    void displayFarmInfo() {
        System.out.println("Farm: " + farmName);
        System.out.println("Number of Animals: " + numberOfAnimals);
    }
}
```

The `numberOfAnimals` field and the `addAnimal()` method have default (package-private) visibility because there is no explicit access modifier specified. So, they're only accessible within the same package, `com.example.animals`. Classes outside this package won't be able to access or modify `numberOfAnimals` directly. For instance, if you try to access `numberOfAnimals` from a class in a different package, it would result in a compilation error: 
```java
package com.example.other;

public class Main {
    public static void main(String[] args) {
        AnimalFarm farm = new AnimalFarm("Happy Farm");
        
        // Compilation error: The field AnimalFarm.numberOfAnimals is not visible
        // farm.numberOfAnimals = 10;
        
        // Compilation error: The method addAnimal() from the type AnimalFarm is not visible
        // farm.addAnimal();
    }
}
```