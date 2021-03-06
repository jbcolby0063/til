# Stack 

```Stack``` is a data structure that follows the "Last In First Out" order. 

So a data that comes in first is the last one to leave. 

A good example will be a browser back button or an undo feature in the word document.

Just think about a ```stack``` of plates as an example:

[![stack1.png](https://i.postimg.cc/sXn9g1xM/stack1.png)](https://postimg.cc/9R7qxmG2)

The opposite of ```stack``` is [queue](https://github.com/jbcolby0063/til/blob/main/algorithms/queue.md).

Here's a simple code for ```stack```:
```python
stack = []

stack.append(5) # [5]
stack.append(2) # [5, 2]
stack.append(3) # [5, 2, 3]
stack.append(7) # [5, 2, 3, 7]
stack.pop() # take out the data on top (7); [5, 2, 3]
stack.append(1) # [5, 2, 3, 1]
stack.append(4) # [5, 2, 3, 1, 4]
stack.pop() # take out the data on top (4); [5, 2, 3, 1]

print(stack) # [5, 2, 3, 1] --> right side (1) is the top part of the stack
```
