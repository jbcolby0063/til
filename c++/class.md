# Class

```Class``` is a user-defined data type that groups attributes (variables for class) and methods (functions for class) to form an object.

Here is a simple example of ```class```:
```c++
#include <iostream>

using namespace std;

// define new data type Student
class Student{
  public: // data members under 'public' can be accessed outside of class, i.e., class users can use data members under 'public'
    Student(); // declare default constructor (optional)
    void setGrade(double x); // declare function setGrade()
    void setName(string n); // declare function setName()
    void getStudentInfo(); // declare function getStudentInfo()
  private: // data members under 'private' cannot be accessed outside of class itself. Only member functions inside the class (e.g. setGrade) can access
    double gpa;
    string name;
};

// define default constructor, i.e., initialize variables
Student::Student(){ // note that there is no data type for constructor function
    gpa = -1.0;
    name = "NoName";
}

// define function setGrade()
void Student::setGrade(double x){ 
    gpa = x; // only member functions can access private members
}

// define function setName()
void Student::setName(string n){
    name = n;
}

// define function getStudentInfo()
void Student::getStudentInfo(){
    cout << name << ": " << gpa << endl;
}

int main()
{
    Student s1; // set new object 's1' as 'Student' class
    
    // print student info before setting it
    s1.getStudentInfo(); // NoName: -1
    
    // set student info
    s1.setGrade(3.5); 
    s1.setName("William");
    
    // print student info after setting
    s1.getStudentInfo(); // William: 3.5

    return 0;
}
```
