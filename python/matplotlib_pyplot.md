# matplotlib.pyplot

```matplotlib.pyplot``` is a module that creates a figure and a plot with labels.

```python 
import matplotlib.pyplot as plt
import numpy as np

f1 = plt.figure(1) 
plt.plot(year, attendance, 'o-b')
plt.xticks(np.arange(year[0], year[-1] + 1, 4))
plt.title("Super Bowl Attendance")
plt.xlabel("year")
plt.ylabel("attendance")
plt.grid()
f1.savefig("super-bowl-attendance-plot.pdf", bbox_inches='tight')

plt.show()
```
