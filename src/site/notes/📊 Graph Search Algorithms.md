---
{"dg-publish":true,"permalink":"/graph-search-algorithms/"}
---

[[📈 Graph Theory\|📈 Graph Theory]] utilizes these search algorithms to determine if nodes are connected (review for terminology)

Note: all algorithms "fail" with negative cycles, meaning the shortest path doesn't exist! 
# 🐋 Depth First Search 
An approach that visit new elements immediately by finding a path between 2 vertices, typically utilizing recursion. It's BEST for finding lots of solutions far from start, but will run forever with infinitely depthless structures. 
```
Algorithm DFS(G, u) {
	initialize VisitedSet, VS
	initilize Stack, S
	S.push(u)
	while S is not empty 
		v <– S.pop()
		if v is not visited in VS 
			mark v as visited in VS 
			for all w adjacent to v
				if w not visited in VS 
				S.push(w)
}
```
## Time / Memory  Complexity 
Linear Time for Graphs: $O(|v| + |e|)$ 
Memory: $O(log n)$ - think about only storing ancestors called, and height of $n$ tree is $logn$ 
- stores all nodes on call stack 
# 🦅 Breath First Search 
Here, the algorithm will visit new elements later by finding the shortest path from start to each vertex, typically implemented with queue. It's BEST for looking for things near the start, but runs forever on trees with ∞ search factor 

```
Q =queue()
s isVisited // boolean or hashset 
Q.enqueue(s)
while Q is not empty 
	v = Q.dequeue() 
	for w adv to v: 
		if w isNotVisited
			w.visited
			Q.enqueue(w)
```
## Time / Memory Complexity 
Linear Time for Graphs: $O(|v| + |e|)$ –– v = no vertices, e = no edges  
Memory: $O(n)$ - think about bottom row of $n$ leaves 
- 1 element on call stack at a time
# 🐇 Dijkstra's Shortest Path
The algorithm build on bfs by utilizing a [[📚 Stack + Queue ADTs#Priority Queues\|priority queue(PQ)]]. The PQ stores distance to vertex from start; complete when you visit all vertices. 

```
Algorithm Dijkstra(G, S) {
	VS = visitedSet 
	DM = HashMap<Vertex, int> 
	PQ = priority queue 
	DM = distance to all v is ∞
	PQ.enqueue(S,0)
	while PQ !empty && VS !full
		(v,d) = PQ.dequeue(); 
		if v !visited 
			v = visited 
			DM[v] = d
			for W adj to v 
				if v !visited
					PQ.enqueue(V, d + distance(v, w))
}
```
## Time / Memory Complexity 
- WC: $O(|E| log(|E|))$ - every edge contributes to PQ, enqueue E times, dequeue E times, implement with heap
- "Standard" : $O(|E| log(|V|))$ - uses a `decrease key` operation to update priority of the queue
	- Optimized by... don't store paths in PQ worse than the one already there 
- BC: $O(|V|log(|V|) + |E|)$
	- Optimized by Fibonacci heaps 
- Traditional: 
	- uses Hash map / array instead of priority queue
