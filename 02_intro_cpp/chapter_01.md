# Chapter 1 — Introduction to Programming in C++

Welcome to **Chapter 1** of your C++ learning journey. This chapter will give you a clear, beginner-friendly overview of what C++ is, how programs are written and run, and introduce the essential building blocks to start coding.

---

## 1. What is C++

C++ is a powerful programming language used to create all kinds of applications — from small tools to video games and complex systems. C++ code is saved in a **source file** that usually ends with the `.cpp` extension.

Your `.cpp` file is plain text; it must be translated into something your computer can run.

---

## 2. The Role of a Compiler

A **compiler** is a program that translates your C++ code into an **executable program** that the computer can understand.

The basic steps are:

1. Write code in a `.cpp` file.
2. Compile it with a compiler.
3. Run the resulting program.

Example using `g++` (Linux/Mac):

```bash
g++ program.cpp -o program
./program
```

Example on Windows (MinGW):

```powershell
g++ program.cpp -o program.exe
program.exe
```

---

## 3. `#include`

`#include` adds extra features to your program. For example:

```cpp
#include <iostream>
```

This allows you to use tools like `std::cout` for displaying text.

---

## 4. The `main` Function

Every C++ program begins execution in the `main` function:

```cpp
int main() {
    // Your instructions here
    return 0; // Indicates successful end
}
```

The `{ }` contain the instructions to be executed.

---

## 5. Your First Program

```cpp
#include <iostream>

int main() {
    std::cout << "Hello, C++!" << std::endl;
    return 0;
}
```

**To run:**

1. Save as `hello.cpp`.
2. Compile: `g++ hello.cpp -o hello`.
3. Run: `./hello` (or `hello.exe` on Windows).

Output:

```
Hello, C++!
```

---

## 6. Comments

Comments are for humans, not the computer. The compiler ignores them.

```cpp
// Single-line comment
/* Multi-line
   comment */
```

---

## 7. Statement Terminator

Most C++ statements end with a semicolon `;`:

```cpp
int age = 20;
```

Omitting it will cause an error.

---

**End of Chapter 1**

You have learned:

* What C++ is and `.cpp` files.
* What a compiler does.
* The role of `#include`.
* The purpose of the `main` function.
* How to write and run a simple program.
* What comments are.
* Why the semicolon matters.

