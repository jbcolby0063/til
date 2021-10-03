# OS

```os``` module in python provides many different functions to interact with the file system.

Let's say there is a ```Python``` folder, which includes ```folder1``` and ```folder2``` folders:
- ```Python```
  - ```folder1```
    - ```myfile.py```
  - ```folder2```
    - ```anotherfile.py```

Then, inside the ```myfile.py```:
```python
import os

# os.getcwd -> shows current directory
# os.chdir -> change directory
print(os.getcwd()) # /Users/myuser/Desktop/Python
os.chdir('folder2') # change the current directory to "folder2"
print(os.getcwd()) # /Users/myuser/Desktop/Python/folder2

# os.path.exists -> checks whether a file or directory exists in current directory
print(os.path.exists('anotherfile.py')) # True
print(os.path.exists('myfile.py')) # False; "myfile.py" does not exist in "folder2"

# os.path.isdir -> checks whether it is directory. Also prints false if the directory does not exist in current directory
# os.path.isfile -> checks whether it is file. Also prints false if the file does not exist in current directory
print(os.path.isdir('anotherfile.py')) # False; not a directory
print(os.path.isfile('anotherfile.py')) # True
print(os.path.isfile('myfile.py')) # False; does not exists in "folder2" 
print(os.path.isdir('/Users/myuser/Desktop/Python/folder2')) # True

# os.listdir -> shows all the files and directories in current directory
print(os.listdir(os.getcwd())) # ['anotherfile.py'] 
```
More ```os``` functions can be found [here](https://docs.python.org/3/library/os.html).

If you want more functions that manipulate paths, look up [os.path module](https://docs.python.org/3/library/os.path.html).
