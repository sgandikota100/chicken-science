---
{"dg-publish":true,"permalink":"/print-steam-class/"}
---

The `PrintStream` [[Classes\|class]] in Java is part of the `java.io` [[Package\|package]] and provides [[Classes#Methods\|methods]] for outputting data to the console or a file. It is commonly used for printing formatted representations of various data types and is especially convenient for writing text-based information to the standard output stream. Let's take a look at a few basic ways to display information: 
# `print()` Method
```java 
System.out.print("Basic"); 
```
# `println()` Method 
```java 
System.out.println("Price using println:\t\t"+price); 
...
Price using println:             25
```
# `printf()` method 
```java 
System.out.printf("Price using printf formatting:%6.2f\t",price); 
... 
Price using printf formatting:   103.43
```
### Format Specifiers
| Format Specifier | Type of Output                    | Example                                          |
| ---------------- | --------------------------------- | ------------------------------------------------ |
| `%c`               | Character                         | A single character: `%c`                           |
|                  |                                   | A single character in a field of 2 spaces: `%2c`   |
| `%d`               | Decimal integer number            | An integer: `%d`                                   |
|                  |                                   | An integer in a field of two spaces: `%2c`         |
| `%f`               | Floating point number             | A floating-point number:`%f`                       |
|                  |                                   | A FPN with 2 digits after the decimal: `%1.2f`     |
| `%e`               | exponential floating number | A FPN in exponential format: `%e`                  |
| `%s`               | String                            | A string formatted to a field of 10 spaces: `%10s` |
|                  |                                   |                                                  |

two arguments = format string + (object/variable/value)
% {flags} {precision} {width} {conversion-character}