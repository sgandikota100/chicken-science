---
{"dg-publish":true,"permalink":"/overloaded-methods/"}
---

When two or more [[Classes#Methods\|methods]] that share same name, but have different parameters (number, data type, or order). Why?? It increases the flexibility of a program. Take a look at the example below. 

```java
static int add(int a, int b){
	System.out.println("This is overloded method #1")
	return a + b; 
}
static int add(int a, int b, int c){
	System.out.println("This is overloded method #2")
	return a + b + c; 
}
static int add(int a, int b, int c, int d){
	System.out.println("This is overloded method #3")
	return a + b + c + d; 
```

The method you want to call depends purely upon what parameters you decide to put in. 