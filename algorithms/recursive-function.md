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
```Recursive Function``` can also be used for the Euclidean Algorithm:
```python
# Euclidean Algorithm is the fastest way to solve for Greatest Common Divisor (GCD) of two integers. 
# Euclidean Algorithm states that when there are two integers of A and B (A > B) and R is the remainder of A / B, GCD(A, B) is equal to GCD(B, R)
# GCD(192, 162) ==> (192, 162) -> (162, 30) -> (30, 12) -> (12, 6) # no more remainder after (12, 6). So the final GCD is 6
# Proof for Euclidean Algorithm: https://m.blog.naver.com/PostView.nhn?blogId=papers&logNo=140207307545&proxyReferer=https:%2F%2Fwww.google.com%2F

def gcd(a, b):
    if a % b == 0: # if there are no more remainders, return b
        return b
    else: # stack up gcd recursive functions
        return gcd(b, a % b) # B, R

print(gcd(192, 162)) # 6
```
