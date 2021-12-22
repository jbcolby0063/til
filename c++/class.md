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
  private: // data members under 'private' cannot be accessed outside of class itself. Only member functions inside the class (e.g. setGrade()) can access
    double gpa;
    string name;
};

// define default constructor, i.e., initialize variables without parameter values
Student::Student()
  : gpa(-1.0), name("NoName") { // note that there is no data type for constructor function

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
You can also create a new object with different initialization values through [a constructor with default parameter values](https://github.com/jbcolby0063/til/blob/main/c%2B%2B/constructor_default.md).

You can declare an object of same class as an attribute. The example below shows a <strong>Student</strong> object "next" is also included in <strong>Student</strong> class under private. Since "next" points to different Student objects, the [pointer](https://github.com/jbcolby0063/til/blob/main/c%2B%2B/pointer.md) is used:
```c++ 
#include <iostream>

using namespace std;

class Student{
    private:
        double score;
        string name;
        Student* next; // a private member (pointer) with same Student class 
    public:
        Student(int setScore = -1.0, string setName = "NoName");
        double getScore();
        string getName();
        void addNext(Student* s);
        void Print();
};


Student::Student(int setScore, string setName): score(setScore), name(setName), next(nullptr) {}

double Student::getScore(){
    return score;
}

string Student::getName(){
    return name;
}

void Student::addNext(Student* s){
    next = s;
}

void Student::Print(){
    cout << name << ": " << score;
    if(next != nullptr){
        cout << ", next student is " << next->getName();
    }
    cout << endl;
}

int main(){
    Student* s1 = new Student(3.8, "James"); // "s1" object
    Student* s2 = new Student(3.6, "Mary"); // "s2" object
    Student* s3 = new Student(2.9, "Hannah"); // "s3" object
    
    Student* cpy = s1; // copy "s1" object in "cpy" object
    
    s1->addNext(s2); // assign "s1" object's next member as "s2" (link to "s2")
    cpy->addNext(s3); // assign "cpy" object's next member as "s3" (link to "s3")
    
    cpy->Print(); // James: 3, next student is Hannah
    s1->Print(); // James: 3, next student is Hannah
    s2->Print(); // Mary: 3
    s3->Print();
    return 0;
}
```
