# C++ Introduction Projects

This repository contains three simple C++ programs, each demonstrating fundamental concepts:

* **hello.cpp**: A basic "Hello, World!" program.
* **io.cpp**: Input and output using `cin` and `cout`.
* **calculator.cpp**: A basic calculator using arithmetic operators and `switch`.

---

## Prerequisites

Before running these examples, you need to have a C++ development environment set up. You can use either:

1. **Visual Studio Code** (with the C/C++ extension) and a MinGW compiler on Windows or GCC on Linux/macOS.
2. **Dev C++** (an all-in-one IDE with bundled MinGW compiler) on Windows.

---

## Installing C++ with Visual Studio Code

### 1. Install Visual Studio Code

* Download and install from: [https://code.visualstudio.com/](https://code.visualstudio.com/)

### 2. Install the C/C++ Extension

1. Open VS Code.
2. Go to **Extensions** (⇧⌘X on macOS or Ctrl+Shift+X on Windows/Linux).
3. Search for **C/C++** by Microsoft and click **Install**.

### 3. Install a C++ Compiler

#### Windows (MinGW)

1. Download the MinGW-w64 installer from: [https://www.mingw-w64.org/](https://www.mingw-w64.org/)
2. Run the installer and choose the latest version, architecture (e.g., `x86_64`), and POSIX threads.
3. Add the `bin` directory of your MinGW installation to the `PATH` environment variable.

   * Example: `C:\Program Files\mingw-w64\mingw64\bin`

#### Linux/macOS (GCC)

* **Linux**: Run `sudo apt update && sudo apt install build-essential`.
* **macOS**: Install Xcode Command Line Tools:

  ```bash
  xcode-select --install
  ```

### 4. Configure VS Code for C++

1. Open the folder containing your `.cpp` files in VS Code.

2. Create a `.vscode` folder at the root.

3. Add a **tasks.json** file to configure build tasks:

   ```json
   {
     "version": "2.0.0",
     "tasks": [
       {
         "label": "build",
         "type": "shell",
         "command": "g++",
         "args": [
           "-g",
           "${file}",
           "-o",
           "${fileBasenameNoExtension}.exe"
         ],
         "group": {
           "kind": "build",
           "isDefault": true
         }
       }
     ]
   }
   ```

4. (Optional) Add a **launch.json** file to enable debugging:

   ```json
   {
     "version": "0.2.0",
     "configurations": [
       {
         "name": "C++ Launch",
         "type": "cppdbg",
         "request": "launch",
         "program": "${fileDirname}/${fileBasenameNoExtension}.exe",
         "args": [],
         "stopAtEntry": false,
         "cwd": "${workspaceFolder}",
         "environment": [],
         "externalConsole": true,
         "MIMode": "gdb",
         "miDebuggerPath": "gdb",
         "setupCommands": [
           {
             "description": "Enable pretty-printing for gdb",
             "text": "-enable-pretty-printing",
             "ignoreFailures": true
           }
         ]
       }
     ]
   }
   ```

---

## Installing Dev C++ on Windows

1. Download the latest version of Dev C++ from: [https://sourceforge.net/projects/orwelldevcpp/](https://sourceforge.net/projects/orwelldevcpp/)
2. Run the installer and follow the prompts.
3. Dev C++ comes with the MinGW compiler bundled, so no additional configuration is needed.

---

## Usage

### Compiling and Running in VS Code

1. Open a `.cpp` file (e.g., `hello.cpp`).
2. Press **Ctrl+Shift+B** (Windows/Linux) or **⇧⌘B** (macOS) to build.
3. Run the resulting executable:

   * On Windows: Open a terminal and run:

     ```bash
     .\hello.exe
     ```
   * On Linux/macOS: In the terminal:

     ```bash
     ./hello
     ```

### Compiling and Running in Dev C++

1. Open Dev C++.
2. Go to **File** > **Open** and select your `.cpp` file.
3. Click **Compile & Run** (or press `F11`).

---

## File Descriptions

### hello.cpp

```cpp
#include <iostream>
int main() {
    std::cout << "Hello, World!" << std::endl;
    return 0;
}
```

A simple program that prints "Hello, World!" to the console.

### io.cpp

```cpp
#include <iostream>
using namespace std;
int main() {
    int number;
    cout << "Enter a number: ";
    cin >> number;
    cout << "You entered: " << number << endl;
    return 0;
}
```

Demonstrates basic input (`cin`) and output (`cout`).

### calculator.cpp

```cpp
#include <iostream>
using namespace std;
int main() {
    int a, b;
    char op;
    cout << "Enter first number: ";
    cin >> a;
    cout << "Enter second number: ";
    cin >> b;
    cout << "Enter operator (+, -, *, /): ";
    cin >> op;

    switch(op) {
        case '+':
            cout << "Result: " << a + b << endl;
            break;
        case '-':
            cout << "Result: " << a - b << endl;
            break;
        case '*':
            cout << "Result: " << a * b << endl;
            break;
        case '/':
            if (b != 0)
                cout << "Result: " << static_cast<double>(a) / b << endl;
            else
                cout << "Error: Division by zero!" << endl;
            break;
        default:
            cout << "Invalid operator!" << endl;
    }
    return 0;
}
```

A basic calculator that performs addition, subtraction, multiplication, and division.
