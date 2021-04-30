# matplotlib.pyplot

```matplotlib.pyplot``` is a module that creates a figure and a plot with labels.

```python 
# Let's assume we have "year" and "attendance" array in here that show all of Super Bowl attendance from 1967 to 2015

import matplotlib.pyplot as plt
import numpy as np

f1 = plt.figure(1) # create a new figure #1
plt.plot(year, attendance, 'o-b') # plot the data using "blue-circle" markers 
plt.xticks(np.arange(year[0], year[-1] + 1, 4)) # set the x-axis ticks from 1967 to 2015 with an increment of 4
plt.title("Super Bowl Attendance")
plt.xlabel("year")
plt.ylabel("attendance")
plt.grid() # configure the grid lines 
f1.savefig("super-bowl-attendance-plot.pdf", bbox_inches='tight') # save the figure as pdf file

plt.show() # show the result
```
Result:

<img src="https://i.postimg.cc/L4P0TXHs/super-bowl-attendance-plot.png" width="550" height="500">

You can look up more ```matplotlib.pyplot``` functions at [matplotlib.pyplot documentation](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.html).
