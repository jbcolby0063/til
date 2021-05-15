# Recursive Function

```Recursive Function``` is a function that calls itself directly. 

```Recursive Function``` uses [stack](https://github.com/jbcolby0063/til/blob/main/algorithms/stack.md) concept since it piles up the functions. 

When you are using ```recursive function```, you need to make sure to put <strong>end condition</strong> for the function in order to prevent it from infinite loop.

```python
def recursive_function(i):
    if i == 101: # end condition for current recursive function
        return 
    print("starting recursive function #", i)
    recursive_function(i + 1) # calls the same function and piles up 
    print("ending recursive function #", i) # once the stack is done, print this ending statement from the top (from i = 100)
    
recursive_function(1) # starting recursive function # 1, ... , starting recursive function # 100, ending recursive function # 100, ... , ending recursive function # 1
```

You can calculate a factorial (n!) using ```recursive function```:
```python
def factorial_recursive(n):
    if n <= 1: # 0!, 1! = 1
        return 1
    return n * factorial_recursive(n - 1) # n! = n * (n - 1)! # stack up the function 


print(factorial_recursive(5)) # 120
```
