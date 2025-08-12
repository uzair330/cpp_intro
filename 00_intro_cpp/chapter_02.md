# Chapter 2 — Variables, Constants, and Basic Data Types

In Chapter 1, you learned how to write and run a basic C++ program. Now it’s time to understand **how to store and work with information** in your programs using variables, constants, and data types.

---

## 1. Variables — Your Data Containers

A **variable** is like a labeled box that stores a value. You can put something inside it, change it, and use it later.

**How to declare a variable:**

```cpp
int age = 20; // type: int, name: age, value: 20
```

* **Type**: what kind of value the variable can hold.
* **Name**: the label you give it.
* **Value**: the data it stores.

You can change a variable’s value:

```cpp
age = 21; // now age stores 21
```

---

## 2. Constants — Unchangeable Values

A **constant** is like a box you cannot change after putting something inside. In C++, you make one using `const`.

```cpp
const int DAYS_IN_WEEK = 7;
```

If you try to change it later:

```cpp
DAYS_IN_WEEK = 8; // ❌ error
```

Constants are useful for fixed values like π (3.14159) or the number of months in a year.

---

## 3. Naming Rules for Variables and Constants

* Only letters, numbers, and underscores `_` are allowed.
* Cannot start with a number.
* No spaces.
* Case-sensitive: `Age` and `age` are different.
* Cannot use C++ keywords like `int`, `return`, `if`.

**Good names:** `score`, `user_name`, `count1`
**Bad names:** `2value`, `my age`, `int`

---

## 4. Basic Data Types

### a) `int`

Stores whole numbers.

```cpp
int apples = 5;
```

### b) `double`

Stores decimal numbers.

```cpp
double price = 3.14;
```

### c) `char`

Stores a single character (inside single quotes `' '`):

```cpp
char grade = 'A';
```

### d) `bool`

Stores `true` or `false`.

```cpp
bool is_sunny = true;
```

---

## 5. Example: Variables and Constants in Action

```cpp
#include <iostream>

int main() {
    int age = 20;           // variable
    const int DAYS = 7;     // constant

    std::cout << "Age: " << age << "\n";
    age = 21; // allowed
    std::cout << "New age: " << age << "\n";

    // DAYS = 8; // ❌ not allowed

    double pi = 3.14159;
    char grade = 'A';
    bool passed = true;

    std::cout << "Pi: " << pi << "\n";
    std::cout << "Grade: " << grade << "\n";
    std::cout << "Passed: " << passed << "\n";

    return 0;
}
```

**Output:**

```
Age: 20
New age: 21
Pi: 3.14159
Grade: A
Passed: 1
```

(Note: `true` prints as `1` and `false` as `0` by default.)

---

**End of Chapter 2**

You now know:

* How to create variables and constants.
* Rules for naming them.
* The main basic data types (`int`, `double`, `char`, `bool`).
* How to use them in a simple program.

In **Chapter 3**, we’ll explore **input/output** so your programs can interact with the user.
