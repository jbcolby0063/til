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
