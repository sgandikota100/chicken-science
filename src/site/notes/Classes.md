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
## Visibility Modifiers for Methods 
- private: makes methods and data fields accessibility only from within its own class 
	- `private int z;`
- default: restricts access to the package 
	- `int z;`
- public: enables unrestricted access 
	- `public int z;`
