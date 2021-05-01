# Overloading Functions and Operators 

```Overloading``` is a way to change the default behavior of Python's built-in functions or operators. It is done by defining a special method in class.

```python
class Time:
    def __init__(self, hour, minute, second):
        self.hour = hour
        self.minute = minute
        self.second = second

    def __str__(self): # changes the return of print()
        return "{0} : {1} : {2}".format(self.hour, self.minute, self.second)
        
time = Time(11, 25, 30)
print(time) # 11 : 25 : 30

```
