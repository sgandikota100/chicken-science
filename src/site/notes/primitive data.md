---
{"dg-publish":true,"permalink":"/primitive-data/"}
---

Primitive data types are predefined by the programming language and represent the simplest units of data that a program can operate on. Unlike complex data types such as objects, primitive types have no methods or properties. This page will focus on its characteristics found in [[☕️ Java\|☕️ Java]]. 
# Categories
There are 8 different primitive data types defined in java, each reserved with a special key word. Each primitive type has a fixed size in memory. And as mentioned these are the building blocks of variables that compose larger, more complex data structures. 

| **Data Type** | **Size** | **Value**                                              | **Default Value** |
| ------------- | -------- | ------------------------------------------------------ | ----------------- |
| `boolean`     | 1 bit    | True/False                                             | `false`                 |
| `byte`        | 1 byte   | -128 to 127                                            | 0                  |
| `short`       | 2 bytes  | -32,768 to 32,767                                      | 0                  |
| `int`         | 4 bytes  | -2 billion to 2 billion                                | 0                  |
| `long`        | 8 bytes  | -9 quintillion to 9 quintillion                        | 0L                  |
| `float`       | 4 bytes  | fractional numbers up to 6/7 digits (3.151692f)        | 0.0f                  |
| `double`      | 8 bytes  | fractional numbers up to 15 digits (3.141593653589793) | 0.0d                  |
| `char`        | 2 bytes  | All Unicode values from 0 to 65,535 ('f')              | `\u0000'                  |

Note: `String` is not a primitive data type, but has a lot of functionality that can be treated like a primitive data type at times! 

Now, the *values* the variables can be changed or updated. Using the keyword `final` doesn't allow you to do that, creating a [[constants\|constant]]. 

Check out [Oracle's page](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/datatypes.html) for more info. 
# Compatibility  
Compatibility of primitive data types refers to the ability of some various types (mentioned above) to interact with each other in expressions and operations without errors. Also note that all primitive data types are compatible with [[🗃 Arrays\|arrays]]. 

`booleans` belong to the "boolean type" are aren't compatible with any other types. 

The other 7 primitive data types belong to the "numeric type". Compatibility is indicate by moving towards the right. All values to the right of a value are compatible with the value itself. 
1. **Character Value**: includes `char`s. 
2. **Intergral Value**: includes `byte`, `short`, `int`, and `long`. 
3. **Floating-Point Values**: includes `float` and `double`. 
	- Note: Why the name? It refers to the fact that the decimal point can be made to "float" anywhere by the adjacent exponent 
	- Also Note: Technically, FPs are "imprecise". The are nearly accurate approximations because they are stored with a finite number of bits. For example `1.0/3.0` is slightly less than $\frac{1}{3}$. 

Now, if you're willing to go against compatibility within one of the values, you can do so with [[Type Casting\|Type Casting]].