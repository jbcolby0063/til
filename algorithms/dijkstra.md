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

Here's a basic code: 
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

def dijkstra(start):
    distance[start] = 0 # set the distance to itself as 0
    visited[start] = True
    for j in graph[start]: # initialize all distance values that are connected to the starting node
        distance[j[0]] = j[1] 
    for i in range(n - 1):
        now = get_smallest_node() # get a node
        visited[now] = True
        for j in graph[now]: # initialize all distance values that are connected to the chosen node
            cost = distance[now] + j[1] # distance value from start node to chosen node + distance from chosen node to connected node
            if cost < distance[j[0]]: # if this value is shorter
                distance[j[0]] = cost # update the distance table

dijkstra(start)

for i in range(1, n + 1):
    if distance[i] == INF:
        print("INFINITY") 
    else:
        print(distance[i])
```

```Dijkstra``` algorithm can also be solved efficiently using [Heap data structure](https://github.com/jbcolby0063/til/blob/main/algorithms/priority-queue.md):
```python
import heapq
import sys
input = sys.stdin.readline
INF = int(10e9)

n, m = map(int, input().split())
start = int(input())
graph = [[] for i in range(n + 1)]
distance = [INF] * (n + 1)

for _ in range(m):
    a, b, c = map(int, input().split())
    graph[a].append((b, c))

def dijkstra(start):
    q = []
    heapq.heappush(q, (0, start)) # distance to itself (start node) is 0 / push it to queue (q)
    distance[start] = 0
    while q: # until queue is empty
        dist, now = heapq.heappop(q) # pop a node that has the shortest distance value
        if distance[now] < dist: # if this chosen node was visited before with shorter value, ignore 
            continue
        for i in graph[now]: # check every node that are connected to the chosen node
            cost = dist + i[1] # distance from start node to chosen node + from chosen node to connected node
            if cost < distance[i[0]]: # if this distance is shorter 
                distance[i[0]] = cost # update distance table
                heapq.heappush(q, (cost, i[0])) # and push it to the priority queue

dijkstra(start)

for i in range(1, n + 1):
    if distance[i] == INF:
        print("INFINITY")
    else:
        print(distance[i])
```
