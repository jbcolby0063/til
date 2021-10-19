# Pointer

```Pointer``` is a variable that stores the memory address.

With the ```pointer```, you can...
  1. easily access address of a memory that stores a certain value
  2. pass array and strings to functions more efficiently
  3. use call by reference method to pass arguments to a function
  4. able to do dynamic memory allocation

Here's one example of using ```pointer```:
```c++
#include <iostream>

using namespace std;

int main()
{
    int a = 11; 
    int *intptr = &a; // 'intptr' points to 'a' memory address
    
    cout << &a << endl; // 0x7fffd695a5fc // 'a' address
    cout << intptr << endl; // 0x7fffd695a5fc // 'a' address with pointer
    cout << *intptr << endl; // 11 // to get the value inside the memory address that the pointer is pointing to, add asterisk(*) in front of pointer
    
    string b = "hello";
    string *strptr = &b; // 'strptr' points to 'b' memory address
    
    cout << strptr << endl; // 0x7fffd695a610
    cout << *strptr << endl; // hello // string value from 'b' address that 'strptr' is pointing to
    

    return 0;
}
```
