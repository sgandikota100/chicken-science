---
{"dg-publish":true,"permalink":"/math-class/"}
---

This isn't your MATH XXXX. This is [[☕️ Java\|☕️ Java]]. 

The `Math` class is a standard utility class in the `java.lang` [[Package\|package]] that provides a collection of [[Classes#Static Methods\|static methods]] for performing mathematical operations. It includes functions for basic arithmetic, exponential, logarithmic, trigonometric, and rounding operations, offering a comprehensive set of mathematical functionalities for Java developers. 

Here are some sample methods I've encountered:
# Exponent Methods 
| Method                    | Meaning                              | Math Way |
| ------------------------- | ------------------------------------ | -------- |
| `expo(double a)`          | returns e raised to the power of a   |          |
| `log(double 1)`           | returns the natural log of a         |          |
| `log10(double a)`         | returns the 10-based logarithim of a |          |
| `pow(double a, double b)` | returns a raised to the power of b   |          |
| `sqrt(double a)`          | returns the square root of a         |          |
# Rounding Methods 
be careful with negative integers! 

| Method                   | Meaning                                                                                                          | Math Way |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------- | -------- |
| `double ceil(double x)`  | x rounded UP to its nearest integer. This integer is retuned as a double value                                   |          |
| `double floor(double x)` | x rounded DOWN to its nearest integer. This integer is returned as a double value                                |          |
| `double rint (double x)` | x is rounded to its nearest integer. If x is equally close to two integers, the even one is returned as a double |          | 
round returns `long` or `int` but `rint` returns `double`
# Math.random()
`math.random()` - returns a pseudorandom double that's >=0 and >1. 
	scale it like this: `int die = (int) (6.0 * Math.random())+1`