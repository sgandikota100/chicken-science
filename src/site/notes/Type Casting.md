---
{"dg-publish":true,"permalink":"/type-casting/"}
---

A **type cast** refers to the process of converting a variable from one data type to another. It enables the programmer to ensure compatibility and perform operations involving different data types by explicitly specifying the desired conversion.

Here's an example: 
```java
// LEGAL 
double distance = 9.0; 
int points = (int) distance; // explicitly 

int measurement = 42; 
double exactVal = measurement; // implicitly


// ILLEGAL 
String cow = "Moo";
int numMoo = (int) cow; // Attempting to cast a String to int (incompatible types)

double distance = 9.0;
int points = distance; // implicitly
```

What makes the last example illegal, considering that both `double` and `int` are numbers and the other way around works? In the first implicit example, the `int` value is implicitly cast to a `double` during assignment because widening conversions (from a smaller data type to a larger one) are done automatically by Java. When converting a `double` to an `int` in Java, the process involves discarding the fractional part of the `double` value. Therefore, to execute this conversion, Java mandates explicit casting to signify that the programmer is intentionally accepting the risk of losing information. This process of discarding the fractional part of a numeric value when converting it to a data type that cannot represent decimal components is known as **truncation**. Once again, it is *discarded*, NOT rounded! 