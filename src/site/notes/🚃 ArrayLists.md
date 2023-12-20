---
{"dg-publish":true,"permalink":"/array-lists/"}
---

`ArrayList` is a special java class that provides a resizable implementation of the array (following the list ADT). The implementation is not covered here, but the overall time complexity is discussed in relation to other list ADTs. 

**Amortized**: Meaning mostly O(1), but sometimes O(n)
# Time Complexity 

| Methods  | ArrayList | LinkedList w/o Tail | LinkedList w/ Tail |
| -------- | --------- | ------------------- | ------------------ |
| AddFront | O(n)      | O(1)                | O(1)               |
| AddBack  | O(1)      | O(n)                | O(n)               |
| AddIndex | O(n)      | O(n)                | O(n)               |
| RemFront | O(n)      | O(1)                | O(1)               |
| RemBack  | O(1)      | O(n)                | O(n)               |
| RemIndex | O(n)      | O(n)                | O(n)               |
| get      | O(1)      | O(n)                | O(n)               |
| clear    | O(n)      | O(n)                | O(n)               | 

# Array List vs. Linked List 

| Array List                            | Linked List                       |
| ------------------------------------- | --------------------------------- |
| better forgetting data                | more efficient?                   |
| computers are optimized for array use | add to both sides (front and end) |
|                                       | not amoritized, always fast       |

