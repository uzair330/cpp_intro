# Installation and Setup

This guide covers installing a C++ development environment using:

* **Visual Studio Code** with MinGW (Windows) or GCC (Linux/macOS)
* **Dev C++** (Windows)

---

## Visual Studio Code Setup

### 1. Install Visual Studio Code

* Download and install from: [https://code.visualstudio.com/](https://code.visualstudio.com/)

### 2. Install the C/C++ Extension

1. Open VS Code.
2. Go to **Extensions** (Ctrl+Shift+X on Windows/Linux or ⇧⌘X on macOS).
3. Search for **C/C++** by Microsoft and click **Install**.

### 3. Install a C++ Compiler

#### Windows (MinGW-w64)

1. Download the MinGW-w64 installer from: [https://www.mingw-w64.org/](https://www.mingw-w64.org/)
2. Run the installer and choose:

   * Architecture: `x86_64`
   * Threads: POSIX
   * Exception: SEH
3. Add the `bin` directory (e.g., `C:\Program Files\mingw-w64\mingw64\bin`) to your `PATH` environment variable.

#### Linux (GCC)

```bash
sudo apt update && sudo apt install build-essential
```

#### macOS (Clang)

```bash
xcode-select --install
```

### 4. Configure VS Code Tasks

Create a `.vscode/tasks.json` in your project root:

```json
{
  "version": "2.0.0",
  "tasks": [
    {
      "label": "build",
      "type": "shell",
      "command": "g++",
      "args": ["-g", "${file}", "-o", "${fileBasenameNoExtension}.exe"],
      "group": { "kind": "build", "isDefault": true }
    }
  ]
}
```

(Optional) Add a `.vscode/launch.json` for debugging if desired.

---

## Dev C++ Setup (Windows)

1. Download Dev C++ from: [https://sourceforge.net/projects/orwelldevcpp/](https://sourceforge.net/projects/orwelldevcpp/)
2. Run the installer and complete the setup.
3. Dev C++ includes a bundled MinGW compiler—no additional steps required.

---

You're all set! Proceed to compile and run your `.cpp` files in either environment.
