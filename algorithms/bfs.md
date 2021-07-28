# Breadth First Search (BFS)

```Breadth First Search (BFS)``` is an algorithm for searching a certain graph or tree data structure.

It starts at the tree root and explores all of the connected nodes before moving to the nodes of the next depth level. 

```BFS``` uses [queue](https://github.com/jbcolby0063/til/blob/main/algorithms/queue.md) data structure and explores nodes in "first in first out" order.

The difference between ```BFS``` and [DFS](https://github.com/jbcolby0063/til/blob/main/algorithms/dfs.md) is that while ```BFS``` explores all the neighbor nodes at the same depth level, 
```DFS``` explores the nodes as deep as possible from the start node. 

So the process will be:
1. Place the start node in queue and mark it as visited.
2. Take out a node from queue and place all the connected nodes that are not visited in queue and mark those as visited. 
3. Repeat #2.

```python
from collections import deque

# data table
graph = [
    [], 
    [2, 3, 8], # node 1
    [1, 7], # node 2
    [1, 4, 5], # node 3
    [3, 5], # node 4
    [3, 4], # node 5
    [7], # node 6
    [2, 6, 8], # node 7
    [1, 7], # node 8
]

# initialize all nodes as unvisited 
visited = [False] * 9

def bfs(graph, start, visited):
    queue = deque([start]) # apply queue
    visited[start] = True # mark as visited
    while queue: # repeat until empty queue 
        v = queue.popleft() # get the node that came first 
        print(v, end='->')
        for i in graph[v]: 
            if not visited[i]:
                queue.append(i) # place all connected nodes that are not visited in queue
                visited[i] = True # mark those as visited 
                 
bfs(graph, 1, visited) # 1->2->3->8->7->4->5->6->
```
[![2021-05-16-9-01-13.png](https://i.postimg.cc/597D8t5w/2021-05-16-9-01-13.png)](https://postimg.cc/fkdHNDrL)

