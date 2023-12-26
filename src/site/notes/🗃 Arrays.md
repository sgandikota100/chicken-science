---
{"dg-publish":true,"permalink":"/arrays/"}
---

An **array** is simply *a collection of items*. In more detail, it's a data structure that allows you to store multiple values of the same type under a single variable name (they're stored in contiguous or neighboring memory locations). Declared with a fixed size, arrays provide a convenient way to organize and manipulate a collection of items. Elements within an array can be accessed using their index. This page goes over arrays in [[☕️ Java\|java]] specifically (Java contains an Array class that is a part of the `java.util` package that extends an object). 

Arrays are also considered [[Reference data types\|reference data types]], meaning when you declare an array variable, you are actually creating a reference to an object that represents the array. The elements of the array, which can be of any data type, are stored as objects in the [[Heap-based Data Structures\|heap memory]]. When you manipulate an array or pass it to a method, you are working with a reference to the array object rather than the actual data. This is in contrast to primitive data types, where the variables directly store the data values.
# 1-D Arrays 
The simplest form of an array is a 1-D array. We can declare (declaration), initialize (initialization), or perform both on an array to first create it and/or assign it a value. Note that if we initialize the array, we MUST set the size of the array implicitly or explicitly. 
```java
// To declare (aka define it) write the type, the name, and the array symbol (brackets)
String[] myChickens;

// We can declare it and asign values to it, seting the size to 3. 
String[] myChickens = {"Chickadee", "Amelia", "Henrietta"};

// Lastly, we can declare it and asign values to it later on while defining the size 
String[] myChickens = new dataType[3];

// later... if we want to assign a value, we can access the array as such: 
myChickens[1] = "Amelia"; 
// Note that arrays are "Zero-Indexed", meaning the first value starts at 0
myChickens[0] = "Chickadee"; 
```

**Is this really all necessary?**
1. Why not make an array of 1000000? 
	- The memory isn't being used right away. You wouldn't buy 100000 hangers would you? 
2. Why isn't the first item in the array item 1?
	- Indexes start at 0 (trust it's for the better)
## Arrays and [[Flow of control#Loops\|loops]]
Let's say your array has a lot of elements; let's just use 5 to demonstrate. 
```java
public class FarmStats {
    public static void main(String[] args) {
        // Declare and initialize array of our animals
        String[] farmAnimals = {"Cow", "Chicken", "Sheep", "Pig", "Horse"};

        // Print each count of each animal
        System.out.println("Farm Animals:");

        System.out.println("1. " + farmAnimals[0]); // Cow
        System.out.println("2. " + farmAnimals[1]); // Chicken
        System.out.println("3. " + farmAnimals[2]); // Sheep
        System.out.println("4. " + farmAnimals[3]); // Pig
        System.out.println("5. " + farmAnimals[4]); // Horse
    }
}
```

With more animals, this block of code can be very long! And if you notice, the only thing changing is the number. With a bit of arithmetic, let's use a loop to access the same array: 

```java
public class FarmStatsWithLoop {
    public static void main(String[] args) {
        // Declare and initialize array of our animals
        String[] farmAnimals = {"Cow", "Chicken", "Sheep", "Pig", "Horse"};

        // Print each count of each animal with for-loop
        System.out.println("Farm Animals:");

        for (int i = 0; i < farmAnimals.length; i++) {
            System.out.println((i + 1) + ". " + farmAnimals[i]);
        }
    }
}
```

Both blocks of code output the same thing, but one is a bit more efficient than the other. We call the top version an "unrolled loop". We can use loops to also assign values to certain indicies of an aray, as seen below: 

```java
// Declare and initialize an array to store square numbers
int[] squareNumbers = new int[10];

// Initialize loop control variable
int i = 0;

// Use a while loop to calculate and insert square numbers into the array
while (i < 10) {
	// We need to be careful with the 0-indexing. The next square number
	// is given by (i + 1) * (i + 1).
	// Calculate it and insert it into the array at index i.
	int square = (i + 1) * (i + 1);
	squareNumbers[i] = square;

	// Increment loop control variable
	i++;
}

// Print the square numbers array
System.out.println("Square Numbers:");
for (int number : squareNumbers) {
	System.out.println(number);
}

// Will print:
// 1
// 4
// 9
// 16
// 25
// 36
// 49
// 64
// 81
// 100
```

To make it a little more *elegant*, you can use a for loop variant known at a "[[Flow of control#`for` each loop|for each]]" loop. Use it once you understand the basics of for loops: 

```java
// Prints exactly the same as the previous example.
for (int square : squareNumbers) {
    // Print the current value of square.
    System.out.println(square);
}
```
## Array Methods
The length attribute in Java arrays returns the number of elements in the array. It provides the size of the array and is accessed using the syntax: 
```java
String[] pigs = {"Peaches", "Hamlet", "S'mores", "Popcorn", "Pancake"};
int arrayLength = pigs.length; // arrayLength is now 5
```

This is the MOST important of the methods. Typically in most classes other array methods are NOT permitted. But cases where you're able to use them, they can be useful. 

The `System.arraycopy()` method is used to copy elements from one array to another. It takes the source array, the starting position in the source array, the destination array, the starting position in the destination array, and the number of elements to be copied.
```java
int[] sourceArr = {1, 2, 3};
int[] destinationArr = new int[3];
System.arraycopy(sourceArr, 0, destinationArr, 0, sourceArr.length);
```

The `Arrays.sort()` method is used for sorting arrays in ascending order. For arrays of primitive types, it uses a dual-pivot [[Divide + Conquer Sorts#🏃‍♀️ Quick Sort\|quicksort algorithm]].
```java
int[] unsortedNumbers = {5, 2, 8, 1, 3};
Arrays.sort(unsortedNumbers); // After sorting: [1, 2, 3, 5, 8]
```

Check out for [Array Class Documentation](https://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html) more methods. 
# 2-D Arrays 
a 2-D array (an "array of arrays") is a structured data type that organizes elements in rows and columns, forming a grid-like structure. Just like 1-D arrays above, we can declare or declare and initialize the array. 
```java
// a general way to declare and initizlze 2-D arrays
data_type[][] array_name = new data_type[x][y];
int[][] arr = new int[10][20];

array_name[row_index][column_index] = {values in row 0}, {values in row n};

// Declare and initialize a 2D array to store cow data (ID, Name, Age)
String[][] redBarnInfo = {
	{"C001", "Bessie", "3"},
	{"C002", "Daisy", "4"},
	{"C003", "Moo Moo", "2"},
	{"C004", "Buttercup", "5"}
};

// in general, to access array elements; add a loop to make it effecient 
x[row_index][column_index]; 

// Displaying cow data using nested loops
System.out.println("Red Barn Data:");

for (int i = 0; i < redBarnInfo.length; i++) {
	System.out.println("Cow ID: " + redBarnInfo[i][0]);
	System.out.println("Cow Name: " + redBarnInfo[i][1]);
	System.out.println("Cow Age: " + redBarnInfo[i][2]);
	System.out.println("---------------------");
}
```

What about accessing the length of the "rows" and "columns"? 
- `array[i].length` : number of values in a row 
- `array.length` : number of rows  
# Swapping first/last element in Array Example
```java
public class Swap {
	public static void swap(int[] v){
		if (v! null) { // this is my precondition
			int temp = v[0]; 
			v[0] = v[v.length - 1]; 
			v[v.length - 1] = temp; // postcondition: values swapped
		}
	}
}
```
if you want to modify an array in another class, you must send a reference of an array and swap that way. 

