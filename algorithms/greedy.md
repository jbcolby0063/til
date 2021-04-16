# Greedy

Greedy is an algorithm that chooses the one that seems to be the best at the moment. 

Greedy algorithm does not guarantee an optimal solution. A path chosen by greedy might seem like the 
best at the moment, but it might turn out another path is better than the greedy one. 

Therefore, it is important to analyze the validity of the greedy method before use. 

```python
# Let's say you have to give the customer $260 change using $100, $20, $10, $5.

n  = 260 
count = 0

# count from the biggest dollar 
array = [100, 20, 10, 5]

for money in array:
    count += n // coin
    n %= coin

print(count)
```
