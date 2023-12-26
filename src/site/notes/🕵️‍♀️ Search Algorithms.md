---
{"dg-publish":true,"permalink":"/search-algorithms/"}
---

Searching Algorithms are designed to check for an element or retrieve an element from any data structure where it is stored.
# Linear Search 
Linear Search finds the position of a target element in a sequential manner. It traverses the collection of elements and compares it with the target until it finds a match. Consider this example with pseudocode using [[🗃 Arrays\|arrays]]: 
```
index = -1
    for i from 0 to length of array - 1:
        if array[i] equals target:
            index = i  // Target found, store the index
            break  // Exit the loop since the target is found
    return index  // Return the final index, -1 if target not found
```

A recap: 
- The `linearSearch` method iterates through each element in the array, comparing it with the target value.
- If a match is found, the method returns the index where the target value is located.

**Time Complexity**: 
$O(n)$, meaning linear time, where the algorithm will traverse an array of $n$ elements before it find a match, WC. 
# Binary Search 
Operating on the principle of divide and conquer, binary search continually divides the search space in half by comparing the target with the middle element of the array: 
```
function binarySearch(array, target):
    low = 0
    high = length of array - 1

    while low <= high:
        mid = (low + high) / 2

        if array[mid] equals target:
            return mid  // Target found, return the index
        else if array[mid] < target:
            low = mid + 1  // Adjust the search range to the right half
        else:
            high = mid - 1  // Adjust the search range to the left half

    return -1  // Target not found

```

- `low` and `high` represent the current range of the search space. The middle index, `mid`, is calculated to divide the search space in half.
- The `while` loop continues as long as the search space is valid (i.e., `low` is less than or equal to `high`).
- If the middle element is equal to the target, the function returns the index. If the middle element is less than the target, the search range is adjusted to the right half. If the middle element is greater than the target, the search range is adjusted to the left half.
- The loop continues until the target is found or the search space is exhausted, at which point the function returns -1 to indicate that the target is not present in the array.

**Time Complexity**
$O(logn)$, meaning logarithmic time, because in the WC of an array of $n$ elements, you are halving what you are searching for