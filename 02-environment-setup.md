# Lesson 02: Setting Up Your C Environment (Desktop & Mobile)

## Overview

Before you can write and run C code, you need two things:
1. A **text editor / IDE** to write your code
2. A **compiler** to translate that code into a program your computer can run

This lesson walks through setting up both on a **desktop (using VS Code)** and on **mobile**, so you can practice C anywhere.

## Setting Up on Desktop (VS Code)

### Step 1: Install a Compiler
VS Code is just an editor — it doesn't compile code by itself. You need a C compiler installed on your machine:

- **Windows**: Install [MinGW](http://mingw-w64.org/) or use the compiler bundled with MSYS2. This gives you access to `gcc` (GNU Compiler Collection).
- **macOS**: Install Xcode Command Line Tools by running this in Terminal:
  ```bash
  xcode-select --install
  ```
- **Linux**: Most distros come with `gcc` pre-installed, or install it via your package manager:
  ```bash
  sudo apt install build-essential
  ```

### Step 2: Verify the Compiler
Open a terminal and run:
```bash
gcc --version
```
If it prints a version number, you're good to go.

### Step 3: Install VS Code
Download it from [code.visualstudio.com](https://code.visualstudio.com/).

### Step 4: Install the C/C++ Extension
In VS Code:
- Go to the Extensions panel (`Ctrl+Shift+X`)
- Search for **"C/C++"** (by Microsoft)
- Click Install

This gives you syntax highlighting, IntelliSense (autocomplete), and debugging support.

### Step 5: Write and Run Your First Program
Create a file named `hello.c`:
```c
#include <stdio.h>

int main() {
    printf("Hello, C!\n");
    return 0;
}
```

Compile and run it from the terminal:
```bash
gcc hello.c -o hello
./hello
```

You should see:
```
Hello, C!
```

## Setting Up on Mobile

You won't get the full VS Code experience on a phone, but there are solid options for practicing C on the go:

| Platform | App/Tool | Notes |
|---|---|---|
| Android | **C4droid** or **Cxxdroid** | Full local compiler on-device, no internet needed |
| Android/iOS | **Programiz Online Compiler** (browser-based) | No install needed, works from any mobile browser |
| Android/iOS | **Replit** (app or browser) | Cloud IDE, supports C, syncs across devices |
| iOS | **Swift Playgrounds** doesn't support C, so browser-based compilers (like Programiz or Replit) are the easiest route on iPhone |

**Tip:** Mobile setups are great for quick practice (like reviewing a lesson on the bus), but a desktop setup is better for serious, longer coding sessions.

## Key Takeaways

- You need both an **editor** and a **compiler** — VS Code alone doesn't run C code.
- `gcc` is the most common C compiler and works the same way across Windows, macOS, and Linux.
- The **C/C++ extension** in VS Code makes writing C much easier.
- On mobile, apps like **C4droid/Cxxdroid** (Android) or browser tools like **Replit/Programiz** (any device) let you practice without a computer.

## Practice Exercise

1. Set up `gcc` and VS Code on your computer (or install a mobile compiler app if you're on the go).
2. Write and run the `hello.c` program above.
3. Modify it to print your own name instead of "Hello, C!", then compile and run it again.

---
*Have fun, take a risk, and get your environment ready — Lesson 03 is coming next! 🚀*
