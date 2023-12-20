---
{"dg-publish":true,"permalink":"/bs-ts/"}
---

Binary Search Trees uses the properties of binary search implemented in a [[🌴 Trees\|🌴 Trees]]
## Get - $O(log n)$ or $O(n)$
Similar to Binary Search; at ANY given node, either node has data or at most 1 subtree somewhat matches criteria for search. Time complexity is $O(log n)$ because we're removing half of the data at each step. The worst case is $O(n)$: consider a degenerate tree whose structure resembles a linked list.
```java 
private node<T> rget(root, data) {
	// base case: is current node null?  
	if (root == null) {
		return null; // --> if data is not in tree, we come here 
	// base case: encounterd data 
	} else if (root.data == data) {
		return root;   
	// recursive case: keep searching 
	} else if (root.data < data)
		root.right = rget(root.right, data)
	// recursive case: keep searching 
	} else {
		root.left = rget(root.left, data)
	}
}
```
## Add - $O(log n)$ or $O(n)$
Adding always adds to a leaf location (and not any other nodes!). Start at root until you reach `null` (if it's found, you DON'T add). Use `get` logic till you reach `null`. Use pointer reinforcement. Average run time is O(log n), worst case is O(n) (when you're adding sequential / sorted data)
```java
private node<T> rAdd(root, data) {
	// 1) finds a spot too add
	if (node == null) {
		newNode = new Node<T> (data); 
		return newNode; 
	// 2) data is already there 
	} else if (node.data == data) {
		// error 
	// 3) Still looking for data
	} else if (node.data < data)
		node.right = radd(node.right, data)
	// 3) Still looking for data
	} else {
		node.left = radd(node.left, data)
	}
	// no change to parrent
	return node
}
```
## Remove -  $O(log n)$ or $O(n)$
Use "Get" logic to find the node to remove. Only can remove from a leaf. Time complexity: avg is $O(log n)$, worst is $O(n)$ 

| `curr / curr.getData()` | what "replaces" `curr` | What happens next?                                             |
| ----------------------- | ---------------------- | ------------------------------------------------- |
| `curr == null`          | data is not in tree    | ERROR! Log in function?                           |
| `curr.data > data`      | `curr`                 | go into left subtree                              |
| `curr.data < data`      | `curr`                 | go into right subree                              |
| `curr.data == data`     | --                     | --                                                | 
| ": Node has 0 kids      | `null`                 | just delete and move on :D                        |
| ": Node has 1 kid       | `curr.left / right`    | connect grandparrent to grandchild                |
| ": Node has 2 kids      | `curr`                 | `curr.data` replaced with pred / succ (see below) |

### Remove w/ 2 Children 
1. Remove data leaving empty node 
2. Remove `pred` / `succ` of empty node. Be sure to check how many kids this node has. However, this node cannot have 2 kids
	- These are only true for **nodes with 2 children**
	- **Predecessor**: node containing largest data smaller than `curr.data`; usually 1 to left, as right as possible 
	- **Successor**: node containing smallest data larger than `curr.data`; usually 1 to right, as left as possible
3. Take `pred` / `succ` and put into empty node
4. Need to return two things w/ function handler 
### Code
```java
/**
* Function Hander deals with pointer reinforcement. 
* Dummy will store removeItem node when found
* Node<T> allows for pointer reinforcement
*/
Node<T> recursiveRemove(T data, Node<T> curr, Node <T> dummy)

public TRemove(T data) {
	Node<T> dummy = new Node (null)
	root = recRemove(data, root, dummy)
	return dummy.data
}

private Node<T> recRemove(T data, node, dummy) {
	if (curr == null) {
		// Data is not in tree!! 
	}

	if (node.data != data) {
		// go left or right; you're still searching
	} 

	if (node.data.equals(data)) {
		dummy.data = node.data
		// delete leaf
		if node has 0 kids:  
			return null
		if node has 1 kid:
			return kid
		if node has 2 kids:
			dummy2 = new Node(null)
			removePredecessor(node.left, dummy2)
			node.data = dummy2.data
			return node
	}
}

private removePredecessor(Node curr, Node dummy) {
	// need to go as right as possible 

	// we are as right as possible 
	if (curr.right == null):
		dummy.data = curr.data
		if (curr.left != null):
			return curr.left
		else:
			return null 
	// we are moving towards the right 
	else: 
		node.right = removePredecessor(curr.right, dummy)
}
```
