# Overloading Functions and Operators 

```Overloading``` is a way to change the default behavior of Python's built-in functions or operators. It is done by defining a special method in class.

```python
class Time:
    def __init__(self, hour, minute, second):
        self.hour = hour
        self.minute = minute
        self.second = second

    def __str__(self): # changes the return of print() for Time class objects
        return "{0} : {1} : {2}".format(self.hour, self.minute, self.second)
    
    def __add__(self, other): # changes the return of + operator for Time class objects 
        return self.hour + other.hour
        
    def __lt__(self, other): # override the behavior of the "less than" operator. Compare two objects based on their minutes.
        return self.minute < other.minute
    
    def __gt__(self, other): # override the behavior of the "greater than" operator. Compare two objects based on their minutes.
        return self.minute > other.minute
    
    def __len__(self): # convert the time into seconds and return that value when len() is invoked
        return self.hour * 3600 + self.minute * 60 + self.second
        
time1 = Time(11, 25, 30)
time2 = Time(12, 30, 30)

print(time1) # 11 : 25 : 30
print(time1 + time2) # 23; time1.hour + time2.hour
print(time2 < time1) # False; time2.minute < time1.minute --> 30 < 25
print(time2 > time1) # True; time2.minute > time1.minute
print(len(time1)) # 41130
```
