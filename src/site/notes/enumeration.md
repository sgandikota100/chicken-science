---
{"dg-publish":true,"permalink":"/enumeration/"}
---

Also known as `enum`, is a special "class" that represents a group of [[constants\|constants]].
```java
public class FarmAnimalsExample {
    // Enum representing types of animals on the farm
    // You will declare the enum in the class, sort of like it's own "method"
    public enum Animal {
        COW,
        DOG,
        CAT,
        DUCK
    }

    public static void main(String[] args) {
        // Using the Enum to declare variables
        Animal farmAnimal1 = Animal.COW;
        Animal farmAnimal2 = Animal.DUCK;

        // Using the Enum in a switch statement
        switch (farmAnimal1) {
            case COW:
                System.out.println("This is a cow.");
                break;
            case DOG:
                System.out.println("This is a dog.");
                break;
            case CAT:
                System.out.println("This is a cat.");
                break;
            case DUCK:
                System.out.println("This is a duck.");
                break;
            default:
                System.out.println("Unknown animal.");
        }

        // Using the Enum in a conditional statement
        if (farmAnimal2 == Animal.DUCK) {
            System.out.println("This is another duck.");
        }
    }
}
```
- The `Animal` Enum represents types of animals on the farm: `COW`, `DOG`, `CAT`, and `DUCK`.
- Variables (`farmAnimal1` and `farmAnimal2`) are declared using the Enum.
- The Enum is used in a switch statement to determine the type of animal and print a corresponding message.
- The Enum is also used in a conditional statement to check if a variable represents a duck.