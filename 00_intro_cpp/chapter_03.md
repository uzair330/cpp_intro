# Chapter 3 — Input and Output in C++

In the previous chapters, you learned how to create variables, constants, and write simple programs. Now, let’s make your programs **interactive** — able to display information to the user and receive input from them.

---

## 1. Output — Showing Information

To display information on the screen, C++ uses `std::cout`.

**Syntax:**

```cpp
std::cout << "Message";
```

* `std::cout` means "console output".
* The `<<` operator sends data to the output.

Example:

```cpp
#include <iostream>

int main() {
    std::cout << "Hello, User!" << std::endl;
    return 0;
}
```

* `std::endl` moves the cursor to a new line.

Output:

```
Hello, User!
```

---

## 2. Input — Getting Data from the User

To take input from the user, C++ uses `std::cin`.

**Syntax:**

```cpp
std::cin >> variable;
```

* `std::cin` means "console input".
* The `>>` operator sends the user’s typed data into a variable.

Example:

```cpp
#include <iostream>

int main() {
    int age;
    std::cout << "Enter your age: ";
    std::cin >> age;
    std::cout << "You are " << age << " years old." << std::endl;
    return 0;
}
```

Sample run:

```
Enter your age: 25
You are 25 years old.
```

---

## 3. Multiple Inputs and Outputs

You can chain multiple `<<` or `>>` operators to work with more than one value.

Example:

```cpp
#include <iostream>

int main() {
    std::string name;
    int age;

    std::cout << "Enter your name: ";
    std::cin >> name;
    std::cout << "Enter your age: ";
    std::cin >> age;

    std::cout << "Hello, " << name << ". You are " << age << " years old." << std::endl;
    return 0;
}
```

Sample run:

```
Enter your name: Ali
Enter your age: 20
Hello, Ali. You are 20 years old.
```

Note: Using `std::cin` with strings stops reading at spaces. For full sentences or multi-word names, you can use `std::getline`.

---

## 4. Using `std::getline` for Full Lines

`std::getline` reads an entire line, including spaces.

Example:

```cpp
#include <iostream>
#include <string>

int main() {
    std::string fullName;
    std::cout << "Enter your full name: ";
    std::getline(std::cin, fullName);
    std::cout << "Hello, " << fullName << "!" << std::endl;
    return 0;
}
```

Sample run:

```
Enter your full name: Ali Khan
Hello, Ali Khan!
```

---

## 5. Mixing `std::cin` and `std::getline`

When using both in the same program, you may need to clear leftover newline characters.

Example:

```cpp
#include <iostream>
#include <string>

int main() {
    int age;
    std::string fullName;

    std::cout << "Enter your age: ";
    std::cin >> age;
    std::cin.ignore(); // Clear leftover newline

    std::cout << "Enter your full name: ";
    std::getline(std::cin, fullName);

    std::cout << fullName << " is " << age << " years old." << std::endl;
    return 0;
}
```

---

**End of Chapter 3**

You have learned:

* How to display output with `std::cout`.
* How to read input with `std::cin`.
* How to handle multiple inputs and outputs.
* How to read full lines using `std::getline`.
* How to handle mixed input types.

In **Chapter 4**, we’ll explore **operators and expressions** so you can perform calculations and make your programs smarter.
