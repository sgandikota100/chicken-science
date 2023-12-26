---
{"dg-publish":true,"permalink":"/varargs/"}
---

(aka Variable Arguments) - a ways to write methods that accept a variable number of arguments. 

You could write [[Classes#Overloaded Methods\|Overloaded Methods]], but this simplifies the complexity. 

```java
/**
 * Calls {@code out.println(arg)} for each {@code arg} in {@code args}.
 * @param out   desired output stream
 * @param args  arguments to print
 */
public static void printlns(PrintStream out, String... args) {
    for (String arg : args) {
        out.println(arg);
    } // for
} // printlns
```