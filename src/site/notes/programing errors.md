---
{"dg-publish":true,"permalink":"/programing-errors/"}
---

Understanding basic programming errors is crucial for writing clear, accurate, and reliable code. 
# Syntax Errors 
Just a grammatical mistake in the program. 
```java
public class SyntaxErrorExample {
    public static void main(String[] args) {
        System.out.println("Hello, World!")  // Missing semicolon
    }
}
```

Java expects statements to be terminated with a semicolon, so when it encounters the absence of it, it generates a syntax error. To correct this error, simply add a semicolon at the end of the line. 
# Runtime Errors 
Errors that are detected when the program is ran, but NOT when it's compiled (ie division by 0)
```java
public class RuntimeErrorExample {
    public static void main(String[] args) {
        int numerator = 10;
        int denominator = 0;
		
        // Attempting to divide by zero
        int result = numerator / denominator;
		
        System.out.println("Result: " + result);
    }
}
```
In this example, the variable `denominator` is assigned a value of 0. When the program attempts to perform the division `numerator / denominator`, it causes a runtime error because dividing by zero is undefined in mathematics. 
To prevent this runtime error, you should ensure that you never attempt to divide by zero or handle such cases using conditional statements to avoid unexpected behavior in your program.
# Logic/Semantic Errors 
Errors not detected during compilation, producing incorrect results. 
```java
public class LogicErrorExample {
    public static void main(String[] args) {
        int num1 = 5;
        int num2 = 7;
        
        // Incorrect logic: swapping values incorrectly
        int temp = num1;
        num1 = num2;
        num2 = temp;

        // Incorrect calculation: adding instead of multiplying
        int result = num1 + num2;

        System.out.println("Result: " + result);
    }
}
```
In this example, there are two logic errors:

1. The intended logic is to swap the values of `num1` and `num2`, but due to a mistake in the swapping code, the values are not exchanged correctly.
2. The calculation of `result` is supposed to be the product of `num1` and `num2`, but due to a mistake, the code adds `num1` and `num2` instead.

When you run this program, it will compile and execute without any syntax or runtime errors, but the result printed to the console will not be what is expected. The output will be:
```
Result: 12
```
To fix these logic errors, you would need to correct the swapping logic and ensure the correct operation (multiplication in this case) is used for calculating the result.