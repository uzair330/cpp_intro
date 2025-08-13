# Chapter 4 — Operators and Expressions in C++

In Chapter 3, you learned how to display output and get input from the user. Now it’s time to learn how to **process** that data using operators and expressions.

---

## 1. What Are Operators?

Operators are symbols that tell the computer to perform specific actions, such as adding numbers or comparing values.

An **expression** is a combination of variables, values, and operators that produces a result.
Example:

```cpp
int sum = 5 + 3; // expression: 5 + 3
```

---

## 2. Types of Operators

### a) Arithmetic Operators

Used for mathematical calculations:

| Operator | Description         | Example | Result |
| -------- | ------------------- | ------- | ------ |
| `+`      | Addition            | `5 + 3` | 8      |
| `-`      | Subtraction         | `5 - 3` | 2      |
| `*`      | Multiplication      | `5 * 3` | 15     |
| `/`      | Division            | `6 / 3` | 2      |
| `%`      | Modulus (remainder) | `7 % 3` | 1      |

Example:

```cpp
int a = 10, b = 3;
std::cout << a + b << std::endl; // 13
std::cout << a % b << std::endl; // 1
```

---

### b) Assignment Operators

Used to assign values to variables:

| Operator | Example  | Same as   |
| -------- | -------- | --------- |
| `=`      | `x = 5`  | —         |
| `+=`     | `x += 3` | `x = x+3` |
| `-=`     | `x -= 3` | `x = x-3` |
| `*=`     | `x *= 3` | `x = x*3` |
| `/=`     | `x /= 3` | `x = x/3` |
| `%=`     | `x %= 3` | `x = x%3` |

---

### c) Comparison Operators

Used to compare two values; result is `true` (1) or `false` (0).

| Operator | Description           | Example  |
| -------- | --------------------- | -------- |
| `==`     | Equal to              | `a == b` |
| `!=`     | Not equal to          | `a != b` |
| `>`      | Greater than          | `a > b`  |
| `<`      | Less than             | `a < b`  |
| `>=`     | Greater than or equal | `a >= b` |
| `<=`     | Less than or equal    | `a <= b` |

---

### d) Logical Operators

Used to combine comparison results:

| Operator | Description                         | Example            |                                           |          |   |          |
| -------- | ----------------------------------- | ------------------ | ----------------------------------------- | -------- | - | -------- |
| `&&`     | Logical AND (true if both are true) | `(a > 0 && b > 0)` |                                           |          |   |          |
| \`       |                                     | \`                 | Logical OR (true if at least one is true) | \`(a > 0 |   | b < 0)\` |
| `!`      | Logical NOT (reverses result)       | `!(a > b)`         |                                           |          |   |          |

---

## 3. Operator Precedence

Some operations happen before others. For example:

```cpp
int result = 5 + 2 * 3; // result is 11, not 21
```

Multiplication happens before addition. You can use parentheses `()` to control order:

```cpp
int result = (5 + 2) * 3; // result is 21
```

---

## 4. Example Program: Simple Calculator

```cpp
#include <iostream>

int main() {
    double num1, num2;
    char op;

    std::cout << "Enter first number: ";
    std::cin >> num1;
    std::cout << "Enter operator (+, -, *, /): ";
    std::cin >> op;
    std::cout << "Enter second number: ";
    std::cin >> num2;

    double result;

    if (op == '+') result = num1 + num2;
    else if (op == '-') result = num1 - num2;
    else if (op == '*') result = num1 * num2;
    else if (op == '/') result = num1 / num2;
    else {
        std::cout << "Invalid operator" << std::endl;
        return 1;
    }

    std::cout << "Result: " << result << std::endl;
    return 0;
}
```

Sample run:

```
Enter first number: 8
Enter operator (+, -, *, /): *
Enter second number: 5
Result: 40
```

---

**End of Chapter 4**

You have learned:

* What operators and expressions are.
* Arithmetic, assignment, comparison, and logical operators.
* Operator precedence.
* How to make a simple calculator.

In **Chapter 5**, we’ll explore **conditional statements** to make decisions in your programs.
