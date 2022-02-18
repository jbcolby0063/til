# Pass Pointer By Reference

If you want to modify a pointer itself through a function, you need to ```pass the pointer by reference```. Since the reference allows a called function (e.g. passPtrByReference()) to modify a local variable from the caller function (e.g. main()), pointer defined from other function can be modified through reference "&".

Without passing pointer by reference:
```c++
#include <iostream>

using namespace std;

void passPtrByReference(int* ptr){ // just passing a pointer
    int* new_ptr = new int[5]{66, 77, 88, 99, 100};
    delete [] ptr;
    ptr = new_ptr;
}

int main()
{
    int* ptr = new int[5]{11, 22, 33, 44, 55};
    
    cout << "Before: " << ptr[1] << endl;
    
    passPtrByReference(ptr);
    
    cout << "After: " << ptr[1] << endl;
    return 0;
}

// output
// Before: 22
// After: 0 // ptr is deleted even though we assigned new_ptr in passPtrByReference() function
```

Passing pointer by reference:
```c++
#include <iostream>

using namespace std;

void passPtrByReference(int* &ptr){ // add & symbol since we want to pass the pointer "ptr" by reference 
    int* new_ptr = new int[5]{66, 77, 88, 99, 100};
    delete [] ptr;
    ptr = new_ptr; // able to modify pointer "ptr" defined from main() function
}

int main()
{
    int* ptr = new int[5]{11, 22, 33, 44, 55};
    
    cout << "Before: " << ptr[1] << endl;
    
    passPtrByReference(ptr);
    
    cout << "After: " << ptr[1] << endl;
    return 0;
}

// output
// Before: 22
// After: 77 // ptr is assigned with new_ptr
```
