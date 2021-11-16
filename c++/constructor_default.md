# Constructor with Default Parameter Values

While the <strong>Student class</strong> from [Class](https://github.com/jbcolby0063/til/blob/main/c%2B%2B/class.md) has a ```constructor``` that takes no argument values, you can also define a ```constructor```
that takes default argument values and create an object with different initialization values using the argument(parameters):
```c++
#include <iostream>

using namespace std;

class Student{
  public: 
    Student(double InitGpa = -1.0, string InitName = "NoName"); // declare default constructor with default parameter values (-1.0 and "NoName")
    void getStudentInfo(); 
  private: 
    double gpa;
    string name;
};

// define default constructor, i.e., initialize variables with argument values
Student::Student(double InitGpa, string InitName)
  : gpa(InitGpa), name(InitName) { 

}

void Student::getStudentInfo(){
    cout << name << ": " << gpa << endl;
}

int main()
{
    Student s1; // set new object 's1' without any argument values (this will be initialized with the default parameter vaules)
    s1.getStudentInfo(); // NoName: -1
    
    Student s2(4.0); // set new object 's2' with only gpa value for argument (then the name value will be initialized with the default parameter value "NoName")
    s2.getStudentInfo(); // NoName: 4
    
    Student s3(3.5, "William"); // set new object 's3' with both gpa and name values for argument 
    s3.getStudentInfo(); // William: 3.5
    
    return 0;
}
```
