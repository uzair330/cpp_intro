# Chapter 6 — Loops in C++

In Chapter 5, we learned how to make programs decide what to do. Now, we’ll see how to make them **repeat actions automatically** using loops.

Loops help you run a block of code multiple times without writing it over and over.

---

## 1. The `while` Loop

Repeats as long as the condition is **true**.

```cpp
while (condition) {
    // code to run repeatedly
}
```

Example:

```cpp
int count = 1;
while (count <= 5) {
    std::cout << "Count: " << count << std::endl;
    count++;
}
```

This prints numbers from 1 to 5.

---

## 2. The `do-while` Loop

Like `while`, but it runs **at least once** before checking the condition.

```cpp
do {
    // code to run
} while (condition);
```

Example:

```cpp
int number = 1;
do {
    std::cout << "Number: " << number << std::endl;
    number++;
} while (number <= 3);
```

---

## 3. The `for` Loop

Best when you know how many times to repeat.

```cpp
for (initialization; condition; update) {
    // code to run repeatedly
}
```

Example:

```cpp
for (int i = 1; i <= 5; i++) {
    std::cout << "i = " << i << std::endl;
}
```

---

## 4. `break` and `continue`

* **`break`** → exits the loop immediately.
* **`continue`** → skips the rest of the code in the current iteration and moves to the next.

Example:

```cpp
for (int i = 1; i <= 5; i++) {
    if (i == 3) {
        continue; // skip 3
    }
    if (i == 5) {
        break; // stop completely
    }
    std::cout << i << std::endl;
}
```

Output:

```
1
2
4
```

---

## 5. Nested Loops

Loops inside loops are used for things like tables.
Example:

```cpp
for (int row = 1; row <= 3; row++) {
    for (int col = 1; col <= 3; col++) {
        std::cout << row << "," << col << "  ";
    }
    std::cout << std::endl;
}
```

Output:

```
1,1  1,2  1,3  
2,1  2,2  2,3  
3,1  3,2  3,3  
```

---

## 6. Example Program: Multiplication Table

```cpp
#include <iostream>

int main() {
    int number;
    std::cout << "Enter a number: ";
    std::cin >> number;

    for (int i = 1; i <= 10; i++) {
        std::cout << number << " x " << i << " = " << (number * i) << std::endl;
    }

    return 0;
}
```

Sample run:

```
Enter a number: 5
5 x 1 = 5
5 x 2 = 10
...
5 x 10 = 50
```

---

**End of Chapter 6**

You have learned:

* `while`, `do-while`, and `for` loops.
* `break` and `continue`.
* Nested loops.
* A real-world example: multiplication table.

In **Chapter 7**, we will explore **functions** to make your code more organized and reusable.
