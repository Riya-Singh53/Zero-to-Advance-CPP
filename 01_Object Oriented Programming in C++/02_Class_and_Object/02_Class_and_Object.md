# 2. Class and Object

Class and Object are the foundation of Object-Oriented Programming (OOP). Every OOP concept starts with understanding these two terms.

---

# What is a Class?

A **Class** is a **blueprint** or **template** for creating objects.

It defines:
- Data Members (Variables)
- Member Functions (Methods)

A class **does not occupy memory** until an object is created.

## Interview Definition

> A class is a user-defined data type that groups data members and member functions into a single unit. It acts as a blueprint for creating objects.

---

## Syntax

```cpp
class ClassName
{
    // Data Members

    // Member Functions
};
```

Example:

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
        cout << name << " " << age << endl;
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
- Data members are initialized.
- Member functions become accessible.

## Interview Definition

> An object is a real-world entity and an instance of a class that occupies memory and can access the class's data members and member functions.

---

## Syntax

```cpp
ClassName objectName;
```

Example

```cpp
Student s1;
```

Here,

- `Student` → Class
- `s1` → Object

---

# Class vs Object

| Class | Object |
|--------|--------|
| Blueprint | Instance of class |
| Logical entity | Physical entity |
| No memory allocated | Memory is allocated |
| Defines properties | Uses properties |
| Created once | Multiple objects can be created |

Example

```
Class  → Car

Objects →
BMW
Audi
Tesla
```

---

# Empty Class

An empty class has no data members and no member functions.

```cpp
class Empty
{
};
```

## Can we create an object?

Yes.

```cpp
Empty e1;
```

## Size of Empty Class

```cpp
#include <iostream>
using namespace std;

class Empty
{
};

int main()
{
    cout << sizeof(Empty);
}
```

Output

```
1
```

### Why is the size 1 byte?

A class cannot have zero size because every object must have a unique memory address.

The compiler allocates **1 byte** so that different objects have different addresses.

---

# Memory Allocation of Objects

A class itself **does not consume memory**.

Memory is allocated **only when an object is created**.

Example

```cpp
class Student
{
public:
    int id;
    float marks;
};
```

Memory allocation:

```
Student (Class)

No Memory
```

When object is created:

```cpp
Student s1;
```

Memory:

```
s1

id
marks
```

Each object gets its own copy of **non-static data members**.

Member functions are stored only once and shared by all objects.

---

# How Object Memory is Organized

Example

```cpp
class Student
{
public:
    int id;
    float marks;

    void display()
    {
    }
};
```

Memory

```
Object s1

-----------------
id
marks
-----------------

display() → Shared
```

Objects store only variables.

Functions are not duplicated for every object.

---

# Object Lifecycle

Every object goes through four stages.

## 1. Declaration

```cpp
Student s1;
```

Memory is allocated.

---

## 2. Initialization

```cpp
s1.id = 101;
```

Values are assigned.

---

## 3. Usage

```cpp
s1.display();
```

Object performs operations.

---

## 4. Destruction

When the object goes out of scope, it is automatically destroyed.

```cpp
{
    Student s1;
}
```

Here `s1` is destroyed after leaving the block.

---

# Accessing Members Using Dot (.) Operator

The dot (`.`) operator is used to access an object's data members and member functions.

Example

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
        cout << name << " " << age;
    }
};

int main()
{
    Student s1;

    s1.name = "Riya";
    s1.age = 23;

    s1.display();
}
```

Output

```
Riya 23
```

---

# Multiple Objects

A class can have any number of objects.

Example

```cpp
Student s1;
Student s2;
Student s3;
```

Each object has its own copy of data members.

```cpp
s1.age = 20;
s2.age = 25;
```

Changing one object does not affect another.

---

# Memory Representation

```
Student Class

id
name

        ↓

-------------------
Object s1
id = 1
name = Riya
-------------------

-------------------
Object s2
id = 2
name = Rahul
-------------------
```

Both objects share the same member functions but have different data.

---

# Object Initialization

Objects can be initialized after creation.

```cpp
Student s1;

s1.name = "Riya";
s1.age = 22;
```

Or using a constructor (covered later).

```cpp
Student s1("Riya", 22);
```

---

# Object Assignment

Objects of the same class can be assigned.

```cpp
Student s1;
Student s2;

s2 = s1;
```

This performs **member-wise copy** by default (shallow copy).

---

# Array of Objects

We can create multiple objects using an array.

```cpp
Student students[5];
```

Each element is a separate object.

Access:

```cpp
students[0].name = "Riya";
students[1].name = "Rahul";
```

---

# Object Size

The size of an object depends on:

- Data members
- Padding (Memory Alignment)
- Virtual Pointer (`vptr`) if virtual functions are used

Member functions do **not** increase object size.

Example

```cpp
class Test
{
public:
    int x;

    void show()
    {
    }
};
```

```
sizeof(Test)

4 Bytes
```

Only `x` occupies memory.

---

# Where are Class Members Stored?

| Member | Stored In |
|---------|-----------|
| Non-static data members | Inside each object |
| Static data members | Separate static memory |
| Member functions | Code/Text segment (shared by all objects) |
| Static member functions | Code/Text segment |
| Virtual table (vtable) | Program memory |
| Virtual pointer (vptr) | Inside each object (if virtual functions exist) |

---

# this Pointer (Introduction)

Every non-static member function receives a hidden pointer called `this`.

Example

```cpp
class Student
{
public:
    int age;

    void setAge(int age)
    {
        this->age = age;
    }
};
```

`this` points to the object that invoked the function.

> **Note:** `this` pointer is explained in detail in a separate topic.

---

# Common Interview Questions

### Does a class occupy memory?

**No.** A class is only a blueprint. Memory is allocated when an object is created.

---

### Do member functions occupy object memory?

**No.** Member functions are stored only once and shared by all objects.

---

### Why is an empty class size 1 byte?

To ensure every object has a unique memory address.

---

### Can multiple objects share data members?

No. Each object has its own copy of non-static data members.

---

### Can multiple objects share member functions?

Yes. Member functions are stored only once and shared by all objects.

---

### Which operator is used to access object members?

The dot (`.`) operator.

---

### Can we create an array of objects?

Yes.

```cpp
Student students[10];
```

---

# Key Points

- Class = Blueprint
- Object = Instance of a class
- Class does not occupy memory.
- Objects occupy memory.
- Objects have separate copies of data members.
- Member functions are shared by all objects.
- Empty class size = 1 byte.
- Objects access members using the dot (`.`) operator.
- Multiple objects can be created from one class.
- Objects are automatically destroyed when they go out of scope.

---

# Quick Revision

✅ Class → Blueprint

✅ Object → Instance of Class

✅ Memory is allocated only for objects.

✅ Member Functions are shared.

✅ Data Members are unique for every object.

✅ Empty Class Size = 1 Byte

✅ Access Members → Dot (`.`) Operator

✅ Multiple Objects can be created from the same class.

✅ Object Lifecycle:
1. Declaration
2. Initialization
3. Usage
4. Destruction
