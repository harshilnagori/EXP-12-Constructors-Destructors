# EXP-12-Constructors-Destructors
# HARSHIL NAGORI
# PRN: 24070123046

# Constructors-and-Destructors

# Study of Constructors and Destructors in C++

## Aim  
To study and implement **Constructors** and **Destructors** in C++.

## Software Used  
- Visual Studio Code (VS Code)  

## Objectives  
- To understand the concept of constructors and destructors in C++.  
- To study how constructors initialize objects automatically.  
- To learn how destructors free memory and clean up resources.  
- To implement programs using both constructors and destructors.  

## Theory  

In C++, **constructors** and **destructors** are special member functions of a class that handle the **lifecycle of objects**.  

### 1. Constructor  
- A constructor is a special function that is invoked automatically when an object of the class is created.  
- It has the same name as the class and does not have a return type.  
- Its main purpose is to initialize data members of the class.  

**Types of Constructors**  
1. **Default Constructor** → Initializes objects with default values.  
2. **Parameterized Constructor** → Accepts arguments and initializes objects with specific values.  
3. **Copy Constructor** → Creates a new object as a copy of an existing object.  

Example in real life: When you **buy a mobile phone**, it comes preloaded with settings (constructor does this initialization).  

### 2. Destructor  
- A destructor is a special function invoked automatically when an object goes out of scope or is explicitly deleted.  
- It has the same name as the class but preceded with a **tilde (~)**.  
- Its purpose is to release memory and resources acquired by the object.  
- Only **one destructor** can exist in a class and it does not take arguments or return values.  

Example in real life: When you **discard your mobile phone**, the destructor ensures proper disposal (cleanup).  

### Key Differences Between Constructor and Destructor  

| Feature        | Constructor | Destructor |
|----------------|-------------|------------|
| Purpose        | Initializes object | Cleans up resources |
| Name           | Same as class | Same as class with `~` prefix |
| Parameters     | Can take parameters | Cannot take parameters |
| Overloading    | Allowed | Not allowed |
| Invocation     | When object is created | When object is destroyed |

## Program Example  

```cpp
#include <iostream>
using namespace std;

class Student {
    string name;
    int age;

public:
    // Default Constructor
    Student() {
        name = "Unknown";
        age = 0;
        cout << "Default Constructor Called" << endl;
    }

    // Parameterized Constructor
    Student(string n, int a) {
        name = n;
        age = a;
        cout << "Parameterized Constructor Called for " << name << endl;
    }

    // Copy Constructor
    Student(const Student &s) {
        name = s.name;
        age = s.age;
        cout << "Copy Constructor Called for " << name << endl;
    }

    // Destructor
    ~Student() {
        cout << "Destructor Called for " << name << endl;
    }

    void display() {
        cout << "Name: " << name << ", Age: " << age << endl;
    }
};

int main() {
    Student s1;                  // Default constructor
    s1.display();

    Student s2("Ishika", 19);    // Parameterized constructor
    s2.display();

    Student s3 = s2;             // Copy constructor
    s3.display();

    return 0; // Destructors will be called automatically for s1, s2, and s3
}


CONCLUSION:

        Constructors are used to initialize objects automatically when they are created. Destructors are used to free resources and memory when objects are destroyed. Together, they ensure efficient object lifecycle management, making programs more reliable and robust.
