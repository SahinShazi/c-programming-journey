# C Programming — Boolean Data Type

> এই নোটটি C Programming-এর Boolean Data Type lesson-এর beginner-friendly documentation। এখানে Boolean কী, `true`/`false`, `0`/`1`, `_Bool`, `bool`, `<stdbool.h>`, conditional logic, Boolean variable এবং practical example আলোচনা করা হয়েছে।

## 1. Boolean Data Type কী?

Boolean এমন একটি data type যার মূল উদ্দেশ্য হলো দুই ধরনের logical state রাখা:

```text
true
false
```

যেমন কোনো user logged in কি না, কোনো light on কি না, password সঠিক কি না—এ ধরনের state Boolean দিয়ে represent করা যায়।

```c
bool isLoggedIn = true;
```

---

## 2. Boolean-এর দুইটি Possible Value

```c
bool isLoggedIn = true;
```

অথবা:

```c
bool isLoggedIn = false;
```

ধারণাগতভাবে:

```text
true  → সত্য / হ্যাঁ / চালু
false → মিথ্যা / না / বন্ধ
```

---

## 3. Boolean কেন দরকার?

Programming-এ অনেক প্রশ্নের উত্তর শুধু হ্যাঁ বা না ধরনের হয়:

```text
User কি logged in?
Password কি সঠিক?
Light কি on?
Game কি over?
User কি verified?
```

এই ধরনের state রাখার জন্য Boolean খুব useful।

---

## 4. Conditional Logic-এ Boolean

Boolean সবচেয়ে বেশি ব্যবহৃত হয় conditional logic-এ।

```c
if (isLoggedIn)
{
    printf("User is logged in
");
}
```

যদি `isLoggedIn` true হয়, condition সত্য হবে।

---

## 5. C Programming-এ Boolean কীভাবে কাজ করে?

C-এর condition system-এ সাধারণভাবে:

```text
0         → false
non-zero  → true
```

তাই:

```c
if (1)
{
    printf("True
");
}
```

condition true হবে।

আবার:

```c
if (0)
{
    printf("True
");
}
```

condition false হবে।

`1` true হিসেবে সবচেয়ে প্রচলিত representation, তবে C-এর condition-এ যেকোনো non-zero value true হিসেবে বিবেচিত হয়।

---

## 6. `_Bool` কী?

C language-এর built-in Boolean type হলো:

```c
_Bool
```

উদাহরণ:

```c
_Bool isLoggedIn = 1;
```

এখানে:

```text
1 → true
0 → false
```

---

## 7. `bool` কী?

C-তে সহজ ও readable ভাবে Boolean ব্যবহার করার জন্য:

```c
bool
```

ব্যবহার করা হয়।

এর জন্য:

```c
#include <stdbool.h>
```

include করতে হয়।

উদাহরণ:

```c
#include <stdio.h>
#include <stdbool.h>

int main()
{
    bool isLoggedIn = true;

    if (isLoggedIn)
    {
        printf("User is logged in\n");
    }

    return 0;
}
```

---

## 8. `<stdbool.h>` Header File

`bool`, `true` এবং `false` সহজভাবে ব্যবহার করার জন্য:

```c
#include <stdbool.h>
```

header file ব্যবহার করা হয়।

তারপর:

```c
bool isLoggedIn = true;
bool isDarkMode = false;
```

লেখা যায়।

---

## 9. Boolean Variable

Boolean variable তৈরি করা যায়:

```c
bool isLoggedIn;
```

তারপর value দেওয়া যায়:

```c
isLoggedIn = true;
```

অথবা:

```c
isLoggedIn = false;
```

একসাথে:

```c
bool isLoggedIn = true;
```

---

## 10. বাস্তব উদাহরণ — Login System

```c
#include <stdio.h>
#include <stdbool.h>

int main()
{
    bool isLoggedIn = true;

    if (isLoggedIn)
    {
        printf("User is logged in\n");
    }
    else
    {
        printf("User is logged out\n");
    }

    return 0;
}
```

Output:

```text
User is logged in
```

যদি:

```c
bool isLoggedIn = false;
```

করা হয়, output হবে:

```text
User is logged out
```

---

## 11. Boolean দিয়ে Application State রাখা

Boolean শুধু login-এর জন্য নয়।

```c
bool isLoggedIn = true;
bool isDarkMode = false;
bool isOnline = true;
bool isAdmin = false;
bool isGameOver = false;
bool isVerified = true;
```

প্রতিটি variable একটি logical state represent করছে।

---

## 12. Comparison থেকে Boolean Result

Comparison-এর ফলাফল true বা false হতে পারে।

উদাহরণ:

```c
5 > 3
```

true।

আর:

```c
5 < 3
```

false।

এটি variable-এ রাখা যায়:

```c
bool result = 5 > 3;
```

এখানে `result` true হবে।

আর:

```c
bool result = 5 < 3;
```

হলে `result` false হবে।

---

## 13. Age Check Example

```c
#include <stdio.h>
#include <stdbool.h>

int main()
{
    int age = 18;

    bool isAdult = age >= 18;

    if (isAdult)
    {
        printf("Adult\n");
    }
    else
    {
        printf("Not an adult\n");
    }

    return 0;
}
```

এখানে:

```c
age >= 18
```

একটি condition, যার result Boolean truth value হিসেবে ব্যবহৃত হয়েছে।

---

## 14. Boolean এবং Integer-এর সম্পর্ক

C-এর condition-এ:

```text
0        → false
1        → true
10       → true
100      → true
-5       → true
```

কারণ zero ছাড়া অন্য value non-zero।

উদাহরণ:

```c
if (10)
{
    printf("True\n");
}
```

এটি true হবে।

---

## 15. Boolean বনাম Integer

Integer সাধারণত সংখ্যা রাখার জন্য:

```c
int age = 18;
```

Boolean logical state রাখার জন্য:

```c
bool isAdult = true;
```

সহজভাবে:

```text
int  → সংখ্যা
bool → true/false state
```

---

## 16. `true` এবং `"true"` এক নয়

এটি মনে রাখা খুব গুরুত্বপূর্ণ।

```c
true
```

একটি Boolean value।

কিন্তু:

```c
"true"
```

একটি String Literal।

একইভাবে:

```c
false
```

Boolean value।

আর:

```c
"false"
```

String।

---

## 17. `bool` Undefined হলে

যদি compiler বলে:

```text
'bool' is undefined
```

তাহলে প্রথমে দেখুন:

```c
#include <stdbool.h>
```

আছে কি না।

সঠিক:

```c
#include <stdio.h>
#include <stdbool.h>

int main()
{
    bool isLoggedIn = true;
}
```

---

## 18. `_Bool` এবং `bool`

C language-এর built-in Boolean type:

```c
_Bool
```

আর:

```c
bool
```

সহজভাবে Boolean ব্যবহার করার জন্য `<stdbool.h>`-এর মাধ্যমে পাওয়া যায়।

Beginner code-এ সাধারণত:

```c
#include <stdbool.h>

bool isLoggedIn = true;
```

লেখা বেশি readable।

---

## 19. Common Mistakes

### Mistake 1 — `<stdbool.h>` include না করা

ভুল:

```c
#include <stdio.h>

bool isLoggedIn = true;
```

সঠিক:

```c
#include <stdio.h>
#include <stdbool.h>

bool isLoggedIn = true;
```

### Mistake 2 — Boolean-এর জায়গায় String ব্যবহার করা

যদি logical state বোঝাতে হয়:

```c
bool isLoggedIn = true;
```

ব্যবহার করা বেশি appropriate।

অন্যদিকে:

```c
char status[] = "true";
```

হলো text, Boolean state নয়।

### Mistake 3 — `true` এবং `"true"` গুলিয়ে ফেলা

```c
true
```

Boolean।

```c
"true"
```

String।

---

## 20. Practice

### Practice 1

একটি Boolean variable তৈরি করুন:

```c
bool isStudent = true;
```

তারপর `if` ব্যবহার করে message print করুন।

### Practice 2

```c
bool isLightOn = false;
```

ব্যবহার করে condition তৈরি করুন।

### Practice 3

Login system তৈরি করুন:

```c
bool isLoggedIn = true;
```

`if-else` ব্যবহার করে:

```text
User is logged in
```

অথবা:

```text
User is logged out
```

print করুন।

### Practice 4

নিচের conditions-এর result নিজে অনুমান করুন:

```c
5 > 3
10 < 2
10 == 10
7 != 7
```

---

## 21. Mini Challenge

একটি program তৈরি করুন যেখানে:

```c
bool isLoggedIn;
```

variable থাকবে।

যদি `true` হয়:

```text
Welcome back!
```

print করবে।

যদি `false` হয়:

```text
Please login first.
```

print করবে।

---

## 22. Quick Revision

### Boolean Header

```c
#include <stdbool.h>
```

### Boolean Variable

```c
bool isLoggedIn = true;
```

### False

```c
bool isLoggedIn = false;
```

### Condition

```c
if (isLoggedIn)
{
    printf("User is logged in\n");
}
```

### C-এর truth concept

```text
0        → false
non-zero → true
```

### Built-in C Boolean type

```c
_Bool
```

### Readable Boolean type

```c
bool
```

### Boolean values

```c
true
false
```

---

## 23. Complete Final Example

```c
#include <stdio.h>
#include <stdbool.h>

int main()
{
    bool isLoggedIn = true;

    if (isLoggedIn)
    {
        printf("User is logged in\n");
    }
    else
    {
        printf("User is logged out\n");
    }

    return 0;
}
```

যদি:

```c
bool isLoggedIn = true;
```

হয়:

```text
User is logged in
```

আর যদি:

```c
bool isLoggedIn = false;
```

হয়:

```text
User is logged out
```

---

# Conclusion

Boolean Data Type programming-এর একটি গুরুত্বপূর্ণ concept।

এটি এমন situation represent করতে ব্যবহৃত হয় যেখানে logical state দুই ধরনের:

```text
True / False
Yes / No
On / Off
Logged In / Logged Out
Available / Unavailable
```

C Programming-এ Boolean-এর built-in type হলো:

```c
_Bool
```

আর সহজ ও readable syntax-এর জন্য:

```c
#include <stdbool.h>
```

এরপর:

```c
bool
true
false
```

ব্যবহার করা যায়।

সবচেয়ে গুরুত্বপূর্ণ বিষয়:

```text
0         → false
non-zero  → true

_Bool     → C-এর built-in Boolean type
bool      → Boolean ব্যবহারের readable form
true      → সত্য
false     → মিথ্যা
```

Boolean ভালোভাবে বুঝে গেলে `if`, `else`, comparison operators এবং পরে logical operators (`&&`, `||`, `!`) শেখা অনেক সহজ হবে।
