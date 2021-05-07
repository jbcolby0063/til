# Dijkstra's Algorithm

```Dijkstra``` algorithm is an algorithm that finds the shortest distance between nodes.

It starts from a certain node and stores the shortest distance value to every other node. 

So the algorithm will be:

1. Set the starting node
2. Make a data table that will store the values of each shortest distance. Initialize all values as INFINITE 
(but, set the distance to itself as 0).
3. Among the nodes that are not visited yet, choose the one that has the shortest distance value 
4. For every nodes that are connected to the chosen node, check if the distance from the start node becomes shorter when it passes through that chosen node. 
If the distance is shorter than the current value, update the data table. 
5. Repeat 3 and 4

[![MN3lL.png](https://i.postimg.cc/Gh8QvwR0/MN3lL.png)](https://postimg.cc/GHRG1f9z)

Here's a simple code: 
```python
import sys
input = sys.stdin.readline
INF = int(1e9) # INFINITE (1 billion)

n, m = map(int, input().split()) # number of nodes and lines between them
start = int(input()) # starting node
graph = [[] for i in range(n + 1)] # data table for the distance information of each line
visited = [False] * (n + 1) # visited data table
distance = [INF] *(n + 1) # data table for storing each shortest distance (initialize as INF first)

for _ in range(m): 
    a, b, c = map(int, input().split()) 
    graph[a].append((b, c)) # from 'a' node to 'b' node, distance is 'c'

def get_smallest_node(): # Among the nodes that are not visited, choose a node that has the smallest distance value 
    min_value = INF
    index = 0
    for i in range(1, n + 1):
        if distance[i] < min_value and not visited[i]:
            min_value = distance[i]
            index = i
    return index
```
