# C Operators

Operator হলো এমন symbol, যা দিয়ে C-তে calculation, comparison ও logical operation করা হয়।

## 1. Arithmetic Operators

| Operator | কাজ |
|---|---|
| `+` | যোগ |
| `-` | বিয়োগ |
| `*` | গুণ |
| `/` | ভাগ |
| `%` | ভাগশেষ |

```c
int a = 10;
int b = 3;

printf("%d\n", a + b); // 13
printf("%d\n", a - b); // 7
printf("%d\n", a * b); // 30
printf("%d\n", a / b); // 3
printf("%d\n", a % b); // 1
```

> Integer division-এ decimal অংশ থাকে না। `10 / 3` → `3`

## 2. Assignment Operators

```c
int x = 10;

x += 5;  // x = x + 5
x -= 5;  // x = x - 5
x *= 5;  // x = x * 5
x /= 5;  // x = x / 5
x %= 5;  // x = x % 5
```

## 3. Increment & Decrement

```c
x++; // x = x + 1
x--; // x = x - 1
```

Pre/Post:

```c
++x; // আগে বাড়াবে
x++; // পরে বাড়াবে

--x; // আগে কমাবে
x--; // পরে কমাবে
```

## 4. Comparison Operators

| Operator | অর্থ |
|---|---|
| `==` | সমান |
| `!=` | সমান নয় |
| `>` | বড় |
| `<` | ছোট |
| `>=` | বড় বা সমান |
| `<=` | ছোট বা সমান |

```c
int a = 10;
int b = 5;

printf("%d\n", a > b);  // 1
printf("%d\n", a == b); // 0
```

C-তে সাধারণভাবে `1` = true এবং `0` = false।

## 5. Logical Operators

### AND `&&`

দুই condition-ই true হতে হবে।

```c
age >= 18 && age <= 30
```

### OR `||`

কমপক্ষে একটি condition true হলেই true।

```c
age < 18 || age > 60
```

### NOT `!`

True-কে false এবং false-কে true করে।

```c
!condition
```

## 6. Bitwise Operators

| Operator | কাজ |
|---|---|
| `&` | Bitwise AND |
| `|` | Bitwise OR |
| `^` | Bitwise XOR |
| `~` | Bitwise NOT |
| `<<` | Left shift |
| `>>` | Right shift |

এগুলো binary/bit level operation-এর জন্য ব্যবহৃত হয়।

## 7. Ternary Operator

ছোট `if-else` এক লাইনে লেখার জন্য:

```c
condition ? value1 : value2;
```

Example:

```c
int age = 20;

char *result = age >= 18 ? "Adult" : "Minor";

printf("%s", result);
```

## 8. `sizeof` Operator

কোনো variable বা data type কত byte memory ব্যবহার করে জানতে:

```c
int x;

printf("%zu", sizeof(x));
printf("%zu", sizeof(int));
```

## 9. Operator Precedence

```c
int result = 10 + 5 * 2;
```

প্রথমে:

```text
5 * 2 = 10
```

তারপর:

```text
10 + 10 = 20
```

Bracket ব্যবহার করলে:

```c
int result = (10 + 5) * 2;
```

Result:

```text
30
```

সাধারণ priority:

```text
()
* / %
+ -
```

## 10. `=` vs `==`

`=` দিয়ে value assign করা হয়:

```c
x = 10;
```

`==` দিয়ে comparison করা হয়:

```c
x == 10;
```

## 11. Common Mistakes

ভুল:

```c
if (x = 10)
```

সঠিক:

```c
if (x == 10)
```

আর:

```c
int x = 5 / 2;
```

Result:

```text
2
```

কারণ এটি integer division।

Float result চাইলে:

```c
float x = 5.0 / 2;
```

Result:

```text
2.5
```

## Quick Revision

```text
Arithmetic   → + - * / %
Assignment   → = += -= *= /= %=
Increment    → ++
Decrement    → --
Comparison   → == != > < >= <=
Logical      → && || !
Bitwise      → & | ^ ~ << >>
Ternary      → ? :
Size         → sizeof
```

## Practice

```c
#include <stdio.h>

int main()
{
    int a = 15;
    int b = 4;

    printf("Sum: %d\n", a + b);
    printf("Remainder: %d\n", a % b);
    printf("Greater: %d\n", a > b);

    return 0;
}
```

নিজে আগে output অনুমান করুন, তারপর program run করুন।
