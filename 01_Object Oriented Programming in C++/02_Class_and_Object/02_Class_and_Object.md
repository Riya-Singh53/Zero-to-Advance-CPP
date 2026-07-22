# 2. Class and Object

## What is a Class?

A **Class** is a **user-defined data type** that acts as a **blueprint (template)** for creating objects.

It defines:
- Data (Data Members / Attributes)
- Functions (Member Functions / Methods)

A class itself **does not occupy memory**. Memory is allocated only when objects of the class are created.

### Interview Definition

> A class is a blueprint or template that defines the properties (data members) and behaviors (member functions) of an object.

---

## Syntax

```cpp
class ClassName
{
    // Data Members

    // Member Functions
};
```

### Example

```cpp
#include <iostream>
using namespace std;

class Student
{
public:
    string name;
    int age;

    void display()
    {
        cout << "Name: " << name << endl;
        cout << "Age : " << age << endl;
    }
};
```

Here,

- `Student` → Class
- `name`, `age` → Data Members
- `display()` → Member Function

---

# What is an Object?

An **Object** is an **instance of a class**.

When an object is created:
- Memory is allocated.
- Data members get their own memory.
- Member functions become accessible.

Think of a class as a blueprint and an object as the real product built from that blueprint.

### Interview Definition

> An object is a real-world instance of a class that occupies memory and can access the data members and member functions defined in the class.

---

## Creating an Object

```cpp
Student s1;
```

Here,

- `Student` → Class
- `s1` → Object

---

## Complete Example

```cpp
#include <iostream>
using namespace std;

class Student
{
public:
    string name;
    int age;

    void display()
    {
        cout << "Name: " << name << endl;
        cout << "Age : " << age << endl;
    }
};

int main()
{
    Student s1;

    s1.name = "Riya";
    s1.age = 22;

    s1.display();

    return 0;
}
```

### Output

```
Name: Riya
Age : 22
```

---

# Class vs Object

| Class | Object |
|--------|--------|
| Blueprint | Instance of a class |
| Logical entity | Physical entity |
| No memory allocated | Memory is allocated |
| Defines data and functions | Uses data and functions |
| Can create many objects | Belongs to one class |

### Real-Life Example

```
Class → Car

Objects →

BMW
Audi
Tesla
```

Another example:

```
Class → Student

Objects →

Riya
Rahul
Ankit
```

---

# Memory Allocation of Objects

A **class does not occupy memory**.

Memory is allocated **only when an object is created**.

Example:

```cpp
class Student
{
public:
    int id;
    char grade;
};

int main()
{
    Student s1;
}
```

Memory is allocated only for:

```
id
grade
```

### Important Points

- Every object has its own copy of **non-static data members**.
- Member functions are **shared** among all objects.
- Static members are shared by all objects.

---

## Memory Representation

```
Class

Student

id
name
display()

        ↓

Object 1 (s1)

id
name

        ↓

Object 2 (s2)

id
name
```

Notice:

- `id` and `name` are different for every object.
- `display()` exists only once in memory and is shared.

---

## Example

```cpp
#include <iostream>
using namespace std;

class Student
{
public:
    int age;
};

int main()
{
    Student s1;
    Student s2;

    s1.age = 20;
    s2.age = 25;

    cout << s1.age << endl;
    cout << s2.age << endl;
}
```

### Output

```
20
25
```

Each object stores its own value.

---

# Object Lifecycle

An object goes through four stages during its lifetime.

```
Creation
      ↓
Initialization
      ↓
Usage
      ↓
Destruction
```

---

## 1. Creation

Memory is allocated.

```cpp
Student s1;
```

---

## 2. Initialization

Values are assigned.

```cpp
s1.age = 22;
```

or

```cpp
Student s1(22);
```

(using a constructor)

---

## 3. Usage

Member functions are called.

```cpp
s1.display();
```

---

## 4. Destruction

When the object goes out of scope, its destructor is automatically called.

```cpp
{
    Student s1;
}

// Destructor is called here.
```

---

# Accessing Members Using Dot (.) Operator

The **dot (`.`) operator** is used to access the data members and member functions of an object.

### Syntax

```cpp
objectName.member;
objectName.function();
```

### Example

```cpp
#include <iostream>
using namespace std;

class Car
{
public:
    string brand;

    void show()
    {
        cout << brand;
    }
};

int main()
{
    Car c1;

    c1.brand = "BMW";
    c1.show();
}
```

### Output

```
BMW
```

---

# Multiple Objects

A class can have **multiple objects**.

Each object has:
- Its own data members
- Shared member functions

### Example

```cpp
#include <iostream>
using namespace std;

class Student
{
public:
    string name;

    void display()
    {
        cout << name << endl;
    }
};

int main()
{
    Student s1;
    Student s2;
    Student s3;

    s1.name = "Riya";
    s2.name = "Rahul";
    s3.name = "Ankit";

    s1.display();
    s2.display();
    s3.display();
}
```

### Output

```
Riya
Rahul
Ankit
```

Each object stores its own data independently.

---

# Real-World Example

```
Class

Employee

Data:
-----
Employee ID
Name
Salary

Functions:
---------
login()
work()
logout()

            ↓

Objects

Employee1
Employee2
Employee3
```

Each employee has different data but uses the same functions.

---

# Frequently Asked Interview Questions

### 1. Does a class occupy memory?

**Answer:** No. A class is only a blueprint. Memory is allocated only when an object is created.

---

### 2. Where are member functions stored?

**Answer:** Member functions are stored only once in memory and are shared by all objects.

---

### 3. Does every object have its own copy of data members?

**Answer:** Yes. Every object has its own copy of non-static data members.

---

### 4. Can one class create multiple objects?

**Answer:** Yes. A single class can create any number of objects.

Example:

```cpp
Student s1;
Student s2;
Student s3;
```

---

### 5. Which operator is used to access class members?

**Answer:** The dot (`.`) operator is used to access members of an object.

Example:

```cpp
s1.display();
s1.age = 22;
```

---

# Quick Revision

## Class

- Blueprint for creating objects.
- Defines data members and member functions.
- Does not occupy memory.

## Object

- Instance of a class.
- Occupies memory.
- Can access class members.

## Memory

- Class → No memory.
- Object → Memory allocated.
- Data members → Separate copy for each object.
- Member functions → Shared by all objects.

## Object Lifecycle

```
Creation
   ↓
Initialization
   ↓
Usage
   ↓
Destruction
```

## Dot (`.`) Operator

```cpp
object.member;
object.function();
```

## Multiple Objects

```cpp
Student s1;
Student s2;
Student s3;
```

Each object has its own data but shares the same member functions.

---

# Interview Summary (30 Seconds)

> A **class** is a blueprint that defines the data members and member functions of an object. It does not occupy memory. An **object** is an instance of a class that occupies memory and can access the class members using the dot (`.`) operator. Each object has its own copy of non-static data members, while member functions are shared among all objects. An object's lifecycle consists of creation, initialization, usage, and destruction.
