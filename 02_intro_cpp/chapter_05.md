# Chapter 5 — Conditional Statements in C++

In previous chapters, we learned how to store and process data. Now it’s time to make our programs **decide what to do** based on certain conditions.

Conditional statements let you control the flow of a program by executing certain code only if specific conditions are true.

---

## 1. The `if` Statement

The simplest form:

```cpp
if (condition) {
    // code runs if condition is true
}
```

Example:

```cpp
int age = 18;
if (age >= 18) {
    std::cout << "You are an adult." << std::endl;
}
```

---

## 2. The `if-else` Statement

Lets you choose between two paths:

```cpp
if (condition) {
    // runs if condition is true
} else {
    // runs if condition is false
}
```

Example:

```cpp
int age = 16;
if (age >= 18) {
    std::cout << "You are an adult." << std::endl;
} else {
    std::cout << "You are not an adult." << std::endl;
}
```

---

## 3. The `if-else if-else` Ladder

Used when there are multiple possible outcomes:

```cpp
if (condition1) {
    // code if condition1 is true
} else if (condition2) {
    // code if condition2 is true
} else {
    // code if none are true
}
```

Example:

```cpp
int marks = 85;
if (marks >= 90) {
    std::cout << "Grade A" << std::endl;
} else if (marks >= 75) {
    std::cout << "Grade B" << std::endl;
} else {
    std::cout << "Grade C" << std::endl;
}
```

---

## 4. Nested `if` Statements

You can put one `if` inside another:

```cpp
int age = 20;
bool hasID = true;

if (age >= 18) {
    if (hasID) {
        std::cout << "You can enter." << std::endl;
    } else {
        std::cout << "Please bring your ID." << std::endl;
    }
}
```

---

## 5. The `switch` Statement

A cleaner way to handle multiple fixed options (especially with integers or characters):

```cpp
switch (expression) {
    case value1:
        // code for value1
        break;
    case value2:
        // code for value2
        break;
    default:
        // code if no cases match
}
```

Example:

```cpp
int day = 3;
switch (day) {
    case 1:
        std::cout << "Monday" << std::endl;
        break;
    case 2:
        std::cout << "Tuesday" << std::endl;
        break;
    case 3:
        std::cout << "Wednesday" << std::endl;
        break;
    default:
        std::cout << "Other day" << std::endl;
}
```

---

## 6. Example Program: Simple Voting Eligibility Checker

```cpp
#include <iostream>

int main() {
    int age;
    std::cout << "Enter your age: ";
    std::cin >> age;

    if (age >= 18) {
        std::cout << "You are eligible to vote." << std::endl;
    } else {
        std::cout << "You are NOT eligible to vote." << std::endl;
    }

    return 0;
}
```

Sample run:

```
Enter your age: 21
You are eligible to vote.
```

---

**End of Chapter 5**

You have learned:

* How to use `if`, `if-else`, `if-else if-else`, and nested `if`.
* How to use `switch` for multiple choices.
* A simple real-world example: voting eligibility.

In **Chapter 6**, we’ll explore **loops** so you can repeat actions without rewriting code.
