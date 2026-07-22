# 1. Introduction to Object-Oriented Programming (OOP)

## What is OOP?

Object-Oriented Programming (OOP) is a programming paradigm that organizes a program using **objects** instead of only functions.

An **object** contains:
- **Data** (called attributes or data members)
- **Functions** (called methods or member functions)

OOP helps us represent real-world entities such as **Car, Student, Bank Account, Employee**, etc.

### Interview Definition

> Object-Oriented Programming (OOP) is a programming paradigm that models software using objects, where each object contains both data and the methods that operate on that data. It makes programs modular, reusable, secure, and easy to maintain.

### Example

```cpp
#include <iostream>
using namespace std;

class Car
{
public:
    string brand;
    int speed;

    void start()
    {
        cout << "Car Started";
    }
};

int main()
{
    Car car1;

    car1.brand = "BMW";
    car1.speed = 120;

    car1.start();

    return 0;
}
```

### Output

```
Car Started
```

In the above example:

- `Car` → Class
- `car1` → Object
- `brand`, `speed` → Data Members
- `start()` → Member Function

---

# Why OOP?

Earlier, programs were written using **Procedural Programming**, where everything was divided into functions.

As software became larger, procedural programming became difficult to manage.

OOP was introduced to solve these problems.

## Problems in Procedural Programming

- Data is not secure.
- Difficult to manage large projects.
- Code reusability is limited.
- Difficult to maintain.
- Functions become highly dependent on each other.
- Not suitable for real-world modeling.

## Why OOP is Better

- Combines data and functions into a single unit (object).
- Provides data security using Encapsulation.
- Supports code reuse using Inheritance.
- Makes software easier to maintain.
- Easier to extend with new features.
- Models real-world objects naturally.

### Interview Answer

> OOP was introduced to overcome the limitations of procedural programming by making software modular, reusable, secure, scalable, and easier to maintain.

---

# Procedural Programming vs Object-Oriented Programming

| Feature | Procedural Programming | Object-Oriented Programming |
|----------|-----------------------|-----------------------------|
| Focus | Functions | Objects |
| Program Structure | Function-based | Class-based |
| Data | Separate from functions | Combined with functions |
| Security | Low | High |
| Reusability | Limited | High |
| Maintenance | Difficult | Easy |
| Scalability | Low | High |
| Real-world Modeling | Difficult | Easy |
| Example Languages | C | C++, Java, Python |

## Procedural Example

```cpp
deposit();
withdraw();
checkBalance();
```

Functions work on data separately.

## OOP Example

```cpp
class BankAccount
{
private:
    int balance;

public:
    void deposit();
    void withdraw();
};
```

Data and functions belong to the same object.

---

# Advantages of OOP

## 1. Code Reusability

Existing code can be reused using **Inheritance**.

Example:

```cpp
class Animal
{
};

class Dog : public Animal
{
};
```

---

## 2. Data Security

Data can be hidden from outside users using **private** access.

```cpp
class Account
{
private:
    int balance;
};
```

Only member functions can access `balance`.

---

## 3. Modularity

Large software is divided into small classes.

Example:

```
Student
Teacher
Employee
Product
Order
```

Each class has its own responsibility.

---

## 4. Easy Maintenance

If one class changes, other classes usually remain unaffected.

This makes debugging and updating easier.

---

## 5. Flexibility

Using **Polymorphism**, the same function can behave differently.

Example:

```
Shape
   |
   |---- Circle
   |
   |---- Rectangle
```

Both implement `draw()` differently.

---

## 6. Easy Debugging

Since classes are independent, finding bugs becomes easier.

---

## 7. Scalability

New classes and features can be added without modifying existing code.

---

## 8. Real-World Modeling

OOP models real-life objects directly.

Examples:

- Car
- Student
- Bank Account
- Employee
- Mobile Phone

---

# Real-World Examples

## Example 1: Car

```
Class:
Car

Attributes:
- brand
- color
- speed

Methods:
- start()
- stop()
- accelerate()
```

Objects:

```
BMW
Audi
Tesla
```

---

## Example 2: Student

```
Class:
Student

Attributes:
- name
- rollNumber
- marks

Methods:
- study()
- attendClass()
- takeExam()
```

Objects:

```
Riya
Rahul
Ankit
```

---

## Example 3: Bank Account

```
Class:
BankAccount

Attributes:
- accountNumber
- balance

Methods:
- deposit()
- withdraw()
- checkBalance()
```

Objects:

```
Savings Account
Current Account
```

---

## Example 4: Mobile Phone

```
Class:
Mobile

Attributes:
- brand
- RAM
- storage

Methods:
- call()
- message()
- camera()
```

Objects:

```
iPhone
Samsung
OnePlus
```

---

## Example 5: Employee

```
Class:
Employee

Attributes:
- id
- name
- salary

Methods:
- work()
- login()
- logout()
```

Objects:

```
Software Engineer
Manager
HR
```

---

# Key Terms

| Term | Meaning |
|------|---------|
| Class | Blueprint for creating objects |
| Object | Instance of a class |
| Attribute | Variable inside a class |
| Method | Function inside a class |
| Instance | Another name for an object |

---

# Interview Summary

**What is OOP?**

> Object-Oriented Programming (OOP) is a programming paradigm that organizes software using objects. Each object contains data and the methods that operate on that data. OOP improves code reusability, security, maintainability, and scalability by using four core principles: Encapsulation, Abstraction, Inheritance, and Polymorphism.

---

# Quick Revision

✅ OOP = Object + Data + Functions

✅ Object = Instance of a Class

✅ Class = Blueprint

✅ OOP solves the limitations of Procedural Programming

### Four Pillars of OOP

- Encapsulation
- Abstraction
- Inheritance
- Polymorphism

### Languages that Support OOP

- C++
- Java
- Python
- C#
- Kotlin
- Swift
