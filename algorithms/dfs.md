# Depth First Search (DFS)

```Depth First Search (DFS)``` is an algorithm for searching a certain graph or tree data structure. 

It starts from the top node of a tree and goes down a given path as far as it can, then backtracks until it finds an unexplored path, and then explores it again. 

```DFS``` uses [recursive function](https://github.com/jbcolby0063/til/blob/main/algorithms/recursive-function.md) and [stacks up](https://github.com/jbcolby0063/til/blob/main/algorithms/stack.md) the nodes on its path. 

The difference between ```DFS``` and [BFS](https://github.com/jbcolby0063/til/blob/main/algorithms/bfs.md) is that while ```DFS``` explores the nodes as deep as possible from the start node, ```BFS``` explores all the neighbor nodes in the same depth level.

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

def dfs(graph, v, visted):
    visited[v] = True # mark the current node as visited
    print(v, end='->')
    for i in graph[v]: # visit the connected nodes
        if not visited[i]:
            dfs(graph, i, visited) # stack the unvisited nodes up (recursive function) and keep going down its path
            # once it hits the end node, it backtracks the stack and explores the nodes that are connected to unvisited nodes

dfs(graph, 1, visited) # 1->2->7->6->8->3->4->5->
```

[![2021-05-16-9-01-13.png](https://i.postimg.cc/597D8t5w/2021-05-16-9-01-13.png)](https://postimg.cc/fkdHNDrL)

