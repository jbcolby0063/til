# Breadth First Search (BFS)

```Breadth First Search (BFS)``` is an algorithm for searching a graph or tree data structure.

It starts at the tree root and explores all of the connected nodes before moving to the nodes of the next depth level. 

```BFS``` uses [queue](https://github.com/jbcolby0063/til/blob/main/algorithms/queue.md) data structure and explores nodes in "first in first out" order.

The difference between ```BFS``` and [DFS](https://github.com/jbcolby0063/til/blob/main/algorithms/dfs.md) is that while ```BFS``` explores all the neighbor nodes at the same depth level, 
```DFS``` explores the nodes as deep as possible from the start node. 

So the process will be:
1. Place the start node in queue and mark it as visited.
2. Take out a node from queue and place all the connected nodes that are not visited in queue and mark those as visited. 
3. Repeat #2.

