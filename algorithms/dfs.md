# Depth First Search (DFS)

```Depth First Search (DFS)``` is an algorithm for searching a graph or tree data structure. 

It starts from the top node of a tree and goes down a given path as far as it can, then backtracks until it finds an unexplored path, and then explores it again. 

```DFS``` uses [recursive function](https://github.com/jbcolby0063/til/blob/main/algorithms/recursive-function.md) and stacks up the nodes on its path. 

So the process will be:
1. Find the start node and mark it as visited.
2. If the connected nodes are not visited yet, stack that node up and visit the node.
3. If the connected nodes are all visited, backtrack the stack and find a node that is connected to unvisited nodes. 
4. Repeat #2 and #3.

Here's a simple code for ```DFS```:
```python
# data table 
graph = [
    [], 
    [2, 3, 8], # all nodes that are connected to no.1 node
    [1, 7], # ... no.2 node
    [1, 4, 5], # ... no.3 node
    [3, 5], # ... no.4 node
    [3, 4], # ... no.5 node
    [7], # ... no.6 node
    [2, 6, 8], # ... no.7 node
    [1, 7] # ... no.8 node
]

visited = [False] * 9 # initialize all nodes as unvisited
```

[![2021-05-16-9-01-13.png](https://i.postimg.cc/597D8t5w/2021-05-16-9-01-13.png)](https://postimg.cc/fkdHNDrL)

