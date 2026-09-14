# Lesson 03: Your First Program — "Hello, World!" Explained

## Overview

"Hello, World!" is the traditional first program in almost every programming language. It's small, but it introduces nearly every basic building block of a C program. In this lesson, we'll break down **every single line** of it.

## The Program

```c
#include <stdio.h>

int main() {
    printf("Hello, World!\n");
    return 0;
}
```

## Line-by-Line Breakdown

### `#include <stdio.h>`
This is a **preprocessor directive**. It tells the compiler to include the **Standard Input/Output library**, which contains functions for printing to the screen and reading input — like `printf()` and `scanf()`.

Think of it as: *"Before you compile my code, go grab this toolbox of ready-made functions."*

### `int main() {`
Every C program must have a `main()` function — it's the **entry point**, meaning this is where the program starts running.

- `int` means this function will return an integer value when it finishes.
- The `{` marks the start of the function's body (the code that runs).

### `printf("Hello, World!\n");`
This is the line that actually does something visible.

- `printf` is a **function** from the `stdio.h` library used to print text to the screen.
- The text inside the double quotes `"Hello, World!"` is called a **string literal** — the exact text to be displayed.
- `\n` is an **escape sequence** that means "new line" — it moves the cursor to the next line after printing, just like pressing Enter.
- The semicolon `;` ends the statement. In C, (almost) every statement must end with a semicolon.

### `return 0;`
This ends the `main()` function and sends the value `0` back to the operating system.

- By convention, `0` means the program ran **successfully**.
- A non-zero value usually signals that some kind of error occurred.

### `}`
This closing brace marks the end of the `main()` function's body.

## How It Runs (Behind the Scenes)

1. The compiler reads `#include <stdio.h>` and pulls in the `printf` function's definition.
2. It compiles your code into an executable file.
3. When you run the executable, the operating system calls `main()`.
4. `printf` sends `"Hello, World!"` to the console, followed by a new line.
5. `main()` returns `0`, telling the OS the program finished without errors.

## Common Mistakes

- **Forgetting the semicolon** after `printf(...)` — this causes a compile error.
- **Missing `#include <stdio.h>`** — without it, the compiler won't recognize `printf`.
- **Mismatched quotes or braces** — always make sure every `"` and `{` has its matching closing partner.
- **Forgetting `\n`** — your output will still work, but multiple `printf` calls will run together on the same line.

## Key Takeaways

- `#include <stdio.h>` gives you access to input/output functions like `printf`.
- `main()` is the required entry point of every C program.
- `printf()` prints text to the screen; `\n` adds a new line.
- `return 0;` signals that the program finished successfully.

## Practice Exercise

Modify the program to print three lines instead of one — your name, your favorite hobby, and today's date — each using its own `printf` statement.

---
*Have fun, take a risk, and see you in the next lesson! 🚀*
