---
{"dg-publish":true,"permalink":"/string-class/"}
---

The String class represents sequences of characters in a sort of "sentence". It provides various methods for manipulating and performing operations on strings. 
# What is a `String`? 
A `String` is simply a sequence of characters, particularly letters, numbers, and symbols. The order and arrangement does matter! Strings are commonly used in programming to represent and manipulate text, providing a versatile way to work with words and sentences in a computer's memory. 
Unlike the `char` datatype, `Strings` are considered to be "objects" (aka instances of a [[Classes\|class]]) or cohesive entities. This distinction allows us to perform various operations and manipulations on the entire string as a unit, such as concatenation, substring extraction, and comparison (aka [[Classes#Methods\|methods]]). A little deeper, when you declare a String variable, you are creating a reference to an object rather than directly storing the data itself. Additionally, the immutability of strings ensures thread safety, and their storage as objects in the heap memory allows for consistent and efficient memory management by the Java Virtual Machine.
## Indicies 
Indicies refer to the position of each character in a string. Strings are zero-indexed, meaning the first character is at index 0, the second at index 1, and so on. This indexing system allows for precise referencing and manipulation of characters in a string using numerical values: 

| Indices   | 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | 10  | 11  |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| String  |C   | o   |r   | n   |     | i   | s   |     | f   | u   | n   | .   |     |     |
Note: the positions START with 0, not 1 
## Concatenation 
Two strings can be "concatenated" (linked) using the + [[Operators\|operator]] or the concat [[String Class#String methods\|String method]]: 
```java 
String greeting = "Hello"; 
String sentence; 
Sentence = greeting +"y'all"; 
System.out.println(Sentence); 
___
String message = "Welcome to the Farm"; 
String message2 = " and the Barn"; 
String newMessage=message.concat(message2); 
System.out.println("The new message is "+newMessage)
// prints "The new message is Welcome to the Farm and the Barn"
```
# String Equality Methods 
| Method                       | Meaning                                          |
| ---------------------------- | ------------------------------------------------ |
| `s1.equals(s2)`              | compares equality of objects in the String class |
| `s1.equalsIgnoreCase(s2)`    | tests for equality ignoring case                 |
| `s1.compartTo(s2)`           | **                                               |
| `s1.compareToIgnoreCase(s2)` | \*\*                                                 |
\* Lexicographic order - the order in [unicode characters] (digits before letter, uppercase before lowercase )
# String Character methods 
| Method                                                 | Description                                                                      | Possible Error                                                                                                                                    |
| ------------------------------------------------------ | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| `<StringName>.charAt()`                                | Returns the character at the specified index within the string                   | `IndexOutOfBoundsException` if the index is negative or greater than or equal to the length of the string.                                        |
| `<StringName>.length()`                                | Returns the length (number of characters) of the string.                         | N/A                                                                                                                                               |
| `<StringName>.substring(int beginIndex)`               | Returns a substring starting from the specified index to the end of the string.  | `IndexOutOfBoundsException` if the beginIndex is negative or greater than the length of the string                                                |
| `<StringName>.substring(int beginIndex, int endIndex)` | Returns a substring starting from the specified beginIndex to endIndex - 1.      | `IndexOutOfBoundsException` if beginIndex is negative, endIndex is greater than the length of the string, or beginIndex is greater than endIndex. |
| `<StringName>.indexOf(String str)`                     | Returns the index of the first occurrence of the specified substring, -1 if none | N/A                                                                                                                                               |
| `<StringName>.toUpperCase()`                           | Converts all characters in the string to uppercase                               | N/A                                                                                                                                               |
| `<StringName>.toLowerCase()`                           | Converts all characters in the string to lowercase.                              | N/A                                                                                                                                                  |

For more methods, visit check out [w3 schools](https://www.w3schools.com/java/java_ref_string.asp )!