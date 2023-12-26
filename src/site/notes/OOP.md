---
{"dg-publish":true,"permalink":"/oop/"}
---

**Object-oriented programming** (OOP) is a powerful programming paradigm that *emphasizes* the concept of objects, which *encapsulate* both data and behavior. By organizing code into reusable classes and creating *objects* (aka instances) from those classes, OOP promotes modular, scalable, and efficient software development. With its key principles of encapsulation, inheritance, and polymorphism, OOP provides a structured approach to designing and implementing complex systems, allowing for better code organization, easier maintenance, and improved code reusability. 
# Classes + Objects
A [[Classes\|class]] is a blueprint for creating objects that contain both data and methods for operating on that data. It defines the attributes and behaviors that objects of that class will possess, such as variables, constants, constructors, and methods. A well-designed Java class encapsulates data and behaviors, ensuring data integrity and code reusability.

Objects are an instance of a class. Objects of the same kind have the same type and belong to the same class. Each object has a defined attribute(s), aka variables. 
```java
String color = "White"
double temp = 20.0 
boolean empty = true 
```

Objects also perform actions, aka methods which affect themselves and other objects. 
```java 
feed(){
	System.out.print("Betsy the cow ate hay")
}
sleep(){
	System.out.print("Betsy the cow is asleep")
}
```
# Principle: encapsulation
Encapsulation involves bundling data (attributes) and the methods operating on that data within a [[Classes\|class]], but not outside of it. This hides the internal implementation, or the details of a class, so that we create a protective barrier. A big portion of implementing this is from [[Classes#Visibility Modifiers\|visibility modifiers]].

Here we can see that the details of `animalType` and `sound` are *encapsulated* within the `Animal` class. The attributes can be accessed and modified only through the given methods.
```java
public class Animal {
    private String animalType;
    private String sound;

    public Animal(String animalType, String sound) {
        this.animalType = animalType;
        this.sound = sound;
    }

    public String getAnimalType() {
        return animalType;
    }

    public void makeSound() {
        System.out.println(sound);
    }
}
```
# Principle: inheritance
[[Inheritance\|Inheritance]] enables the creation of a new class by inheriting the properties and behaviors of an existing class to promote a more structured hierarchy and code reuse. 
# Principle: polymorphism
Polymorphism allows objects of different types to be treated as objects of a common type. This enables flexibility in programming by facilitating the use of a single interface to represent various implementations. There are a few various cases which we can explore below: 

1. [[Classes#Overloaded Methods\|method overloading]]: where multiple methods with the same name but different parameter types or numbers can coexist in a class. 
```java
class Animal {
    void makeSound() {
        System.out.println("Generic Animal Sound");
    }
}

class Dog extends Animal {
    void makeSound() {
        System.out.println("Woof!");
    }
}
```

In this example, the `makeSound` method is overridden in the `Dog` class to provide a specific implementation.

2. [[Interfaces\|Interfaces]] **Polymorphism**: We can use interfaces to act in a way that demonstrates polymorphism by showing how two implementing classes can be referred to as the same class 
```java
interface Shape {
    void draw();
}

class Circle implements Shape {
    void draw() {
        System.out.println("Circle: o ");
    }
}

class Square implements Shape {
    void draw() {
        System.out.println("Square: □ ");
    }
}
```

3. [[💡Generics\|💡Generics]]: allow the implementation of different types through one piece of code 