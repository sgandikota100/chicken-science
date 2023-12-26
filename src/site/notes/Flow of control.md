---
{"dg-publish":true,"permalink":"/flow-of-control/"}
---

The order in which a program performs actions by *branching*, *decisions*, and *selection* *statements* 
# Branching
Branching allows a program to make decisions and execute specific sets of instructions based on certain conditions. This capability introduces a level of adaptability, enabling the code to respond differently to various scenarios or inputs.
## If-Else Statement 
The basic version of and If-Else statement is designed to make decisions based on whether a specified condition is true or false: 
```java 
if (balance >= 0) {
	balance = balance + (INTEREST_RATE * balance) / 12
} else {
	balance = balance - OVERDRAWN_PENALTY; 
} // Note: The braces are formatted to show the distinction between conditions and code blocks. For statements where there the "code block" is 1 line long, braces are not required, but it is good format to do so. 
```

In some cases, you might encounter`if (even)` which simply is a shortened (and more convent) way to say `if (even == true)`. 

**Common Mistakes**
- Forgetting the condition needs () 
- Adding a ';' to the condition ([[programing errors#Logic Semantic Errors\|logical error]])

A more complex example is an If-Elseif-Else statement, which allows you to test various conditions. 
```java
if (score >= 90) {
            System.out.println("A");
        } else if (score >= 80) {
            System.out.println("B");
        } else if (score >= 70) {
            System.out.println("C");
        } else {
            System.out.println("Fail");
        }
```

Note that adding an `else` forces the code to execute that portion if none of the conditions are met. This can change the outcome of the code if omitted. 
### A deeper look at the condition
A condition, at the end of the day is a boolean expression that must evaluate to true or false. It is subsequent to the rules of [[👻 Boolean Algebra\|boolean algebra]] using [[Operators#Comparision Operators\|comparison operators]]. 

You can also use [[Operators#Logical Operators\|logical operators]] to create compound boolean expressions: 
```java 
if ((score > 0) && (score <=100))

// This is illegal because Java does not support chaining comparision operators in this way
if (0 < score <= 100)
```

To help keep track of various outcome, use a [[Propositional Logic#Truth Tables\|truth table]]. 
## Switch Statement
The Switch statement is useful when there is a need to check the value of a variable against multiple possible cases. 

The example lists out the syntax below:  

```java 
switch (numberOfPuppies){ // lists the condition (usually variable) to compare 
	case 1: // case denotes the possible value; the first match is executed
		System.out.println("Congradulations!"); 
		break; // keword break ends the execution
	case 2: 
		System.out.println("Wow, twins!!"); 
		break; 
	case 3: 
		System.out.println("Wow, Triplets!!!");
		break; 
	case 4: // note this case! becase break is not encounted...
	case 5: //... the following case is also executed
		System.out.print("Unvelievable! ");
		System.out.println(numberOfBabies+" babies!!"); 
		break; 
	default: // if no match is found nothing is executed. A default create a condition
			// that always runs
		System.out.println("You don't have puppies do you?!?"); 
		break;
}
```
### Switch or Else-If statements? 
Although sometimes they can be used interchangeably, in more complex examples, it all depends on how you want the code to flow. 

An **else-if** statement offers greater flexibility, making it adept at managing intricate conditions that encompass ranges or multiple variables. This construct is well-suited for scenarios in which conditions exhibit diversity and cannot be straightforwardly articulated through basic equality comparisons. The **switch** statement proves advantageous in situations where a singular expression holds various distinct values, and there is a need to execute diverse code blocks based on these values. This construct is frequently employed to enhance code readability, especially when dealing with multiple constants in a comparison scenario.

Also note now the two are executed: the **switch** statement assesses the expression once and contrasts the outcome with each case value. It initiates the code block linked with the initial matching case. The evaluation process stops upon finding a match, and the examination of other cases does not occur unless a `break` statement is encountered. Within an **else-if** statement conditions undergo sequential evaluation. Upon identifying the first true condition, the corresponding code block is executed, and the subsequent conditions within the ladder are bypassed. This sequential evaluation contrasts with the behavior of a **switch** statement, where automatic skipping occurs upon encountering a matching case.
# Loops
Loops are vital components that enable the repetition of blocks of code (without being redundant), improving efficiency. 
## The `while` loop
A `while` loop is a loop that continues to iterate as long as the given condition remains true, allowing for dynamic and flexible repetition in the code. Let's take a look at an example
```java 
System.out.println("Let's see if we have enough eggs for a cake")
int count = 0; 

while (count < 3){
	System.out.println("Count is: " + count); 
	count++; 
}

System.out.println("We have enough eggs! Final count is " + count); 
```

1. We initialize a variable `count` to 0. This variable will be used to control the number of iterations in the loop
2. The `while` loop is defined with the condition `count < 3`. As long as this condition is true, the code inside the loop will be executed
3. Inside the loop, we print the current value of `count` using `System.out.println("Count is: " + count);`
4. We increment the value of `count` using `count++`. This step is important to ensure that the loop eventually terminates (otherwise we would have an infinite loop or a loop that runs forever). 
5. The loop continues iterating until the condition `count < 4` becomes false.
6. After the loop, we have code outside the loop, in this case, a simple message indicating that the loop has finished.

The code prints: 
```
Count is 0
Count is 1
Count is 2
We have enough eggs! Final count is 3
```
Even though the last print statement says we have 2 eggs, the count is incremented *after* the print statement, meaning when the loop condition is checked, we don't have *2 eggs*, but *3 eggs*! In some cases, you won't have a final print statement, so you'll have to deduce what the final values of variables will be.
## The do-while loop 
Unlike the "while" loop, which evaluates the condition before entering the loop, the "do-while" loop guarantees that the code block is executed at least once before checking the condition for further iterations.
```java
int count = 1; 
do {
	System.out.println("Count is: "+count); 
	count++; 
} while (count < 11); 
```
1. We initialize a variable, `count`, and assigns it the value of `1`. This variable will be used to control the loop
2. The code inside the curly braces `{ ... }` is the block of code to be executed; execute this no matter what
3. The loop condition `while (count < 11)` is checked after the code block has been executed.
4. The loop will continue to execute as long as the condition `count < 11` is true.

The code above will print out 10 times. 

A off-by-one error is a common logical error that occurs with do-while and while loops. Make sure you determine the correct increment that the loop will run for! 
## The `for` loop 
A `for` loop is a versatile control structure designed for efficiently iterating over a range of values. It consists of three components within its parentheses: the initialization of a control variable, the loop condition, and the increment or decrement of the control variable. The loop executes the specified block of code repeatedly as long as the condition remains true. 
here are three essential conditions specified within the parentheses: 
- The **initialization** is the first part of a `for` loop and is executed only once at the beginning. It typically initializes a control variable, which is used to control the loop's execution.
- The **condition** is a boolean expression that determines whether the loop should continue executing or not. If the condition is true, the loop continues; if it is false, the loop exits.
- The **increment** / **decrement** statement is executed after each iteration of the loop. It updates the control variable and is crucial for ensuring that the loop progresses towards its termination.
```java
// Using a for loop to count tractors on the farm
for(int tractors = 0; tractors < 5; tractors++){
	System.out.println("Tractor No. " + tractors + "!"); 
}
System.out.println("We have too many tractors!");

// Using a for loop to count animals on the farm
for (int animalCount = 1; animalCount <= 5; animalCount++) {
	System.out.println("There are " + animalCount + " animals on the farm.");
}
System.out.println("Counting complete. The farm is bustling with activity!");
```

## `for` each loop
a `for` each loop, also known as an enhanced `for` loop, provides a concise and readable way to iterate through elements in an [[🗃 Arrays\|array]] or any [[☕️ Java#Iterators\|iterable]] object, such as collections or lists. It simplifies the syntax by eliminating explicit indicies (the three loop conditions!), reducing the chances of indexing errors. 
```java
// Declare and initialize an array of cow names
String[] myMooers = {"Bessie", "Daisy", "Moo Moo", "Buttercup", "Clarabelle"};

// Displaying cow names using a for-each loop
System.out.println("The Mooers:");

// For each VALUE in the Array... print the name
for (String cowName : myMooers) { // cowName is the local variable initilizated in the loop
	System.out.println(cowName);
}
```
# `break` and `continue` 
The`break` statement is a control flow statement in Java used to prematurely exit a loop. When encountered, it immediately terminates the loop's execution and transfers control to the first statement following the loop. It is important to note that in general, it is not common to use these key words, but it is bad practice to use numerous `breaks` and/or `countinues`.
```java
int animalCount = 0;
int targetCount = 5;

while (true) {
    animalCount++;
    System.out.println("Counted " + animalCount + " animals on the farm.");

    if (animalCount == targetCount) {
        System.out.println("Target count reached. Exiting the loop.");
        break;
    }
}
```
This prints out: 
```
Counted 1 animals on the farm.
Counted 2 animals on the farm.
Counted 3 animals on the farm.
Counted 4 animals on the farm.
Counted 5 animals on the farm.
Target count reached. Exiting the loop.
```

The `continue` statement is a control flow statement in Java used to skip the remaining code within a loop for the current iteration. It then moves to the next iteration of the loop.
```java 
for (int animal = 1; animal <= 5; animal++) {
    if (animal == 3) {
        System.out.println("Skipping counting for animal 3.");
        continue;
    }
    System.out.println("Counted " + animal + " animals on the farm.");
}
```
This prints out:
```
Counted 1 animals on the farm.
Counted 2 animals on the farm.
Skipping counting for animal 3.
Counted 4 animals on the farm.
Counted 5 animals on the farm.
```