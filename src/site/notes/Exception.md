---
{"dg-publish":true,"permalink":"/exception/"}
---

An event that occurs during the execution of a program that encounters an error of some exceptional situation. 
# Default Exception Message 
```java 
Exception in thread "main" java.lang.NullPointerException: Cannot invoke "String.length()" because "<local0>" is null
	at Exception.exception(Exception.java:9)
	at Exception.main(Exception.java:3)
```
- **Line 1** : error name: what occurred 
- **Line 2 + 3** :  stack trace (tells user which methods were active)
We have to deal with exceptions in two ways: Avoid to try-catch (see below)
## Checked Exceptions 
Checked exceptions must be explicitly caught or propagated by the programmer
## Unchecked Exceptions
Unchecked exceptions may or may not be handled by the programmer.
# Avoid Them 
Make sure you do not invoke the members. For example, taking the prior exception, you can short circuit and check conditions
```java
// avoid NPE via short circuiting
if ((s != null) && (s.length() > 1)) {
    System.out.println("string length > 1");
} // if
```
# try / try-catch block
You can handle the exceptions using this block: 
```java
try {
    if (s.length() > 1)) {
        System.out.println("string length > 1");
    } // if
} catch (NullPointerException npe) {
    System.out.println("a NullPointerException was thrown!");
} // try
System.out.println("I will print regardless of the value of s.");
```

