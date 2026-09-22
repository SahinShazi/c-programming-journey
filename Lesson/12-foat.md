# Lesson 11: float, double এবং long double — C Programming

## Floating Point কী?

আগের lesson-এ আমরা দেখেছি `int` দিয়ে শুধু
**পূর্ণ সংখ্যা** (যেমন 1, 2, 100) store করা যায়।

কিন্তু যদি দশমিক সংখ্যা (যেমন 3.14, 549.56,
-27.8) store করতে হয়? তখন দরকার হয়
**Floating Point** ডেটা টাইপ।

C-তে তিনটা floating point ডেটা টাইপ আছে:

| Type          | সাইজ       | নির্ভুলতা         |
|---------------|------------|-------------------|
| `float`       | 4 bytes    | ~6-7 দশমিক ঘর    |
| `double`      | 8 bytes    | ~15-16 দশমিক ঘর  |
| `long double` | 12-16 bytes| ~18-19 দশমিক ঘর  |

---

## 1. float

**সাইজ:** 4 bytes
**Format Specifier:** `%f`

```c
float f = 549.56F;
```

> 💡 `float` value-এর শেষে `F` বা `f` লেখার
> অভ্যাস করো। না লিখলেও কাজ করে, কিন্তু
> compiler warning আসতে পারে।

---

## 2. double

**সাইজ:** 8 bytes
**Format Specifier:** `%lf`

```c
double d = 489273883.77;
```

> 💡 `double` মানে "double precision" — `float`-এর
> চেয়ে দ্বিগুণ নির্ভুল। বেশিরভাগ ক্ষেত্রে
> `double` ব্যবহার করাই ভালো অভ্যাস।

---

## 3. long double

**সাইজ:** 12 বা 16 bytes (system-এর উপর নির্ভর করে)
**Format Specifier:** `%Lf` (বড় হাতের L)

```c
long double ld = 483836821992.3838;
```

> ⚠️ `%Lf` লেখার সময় `L` অবশ্যই **বড় হাতের**
> হতে হবে। ছোট হাতের `l` দিলে কাজ করবে না।

---

## সম্পূর্ণ কোড

```c
#include <stdio.h>

int main()
{
    // Float - %f
    float f = 549.56F;
    printf("Float - %f\n", f);

    // Double - %lf
    double d = 489273883.77;
    printf("Double - %lf\n", d);

    // Long Double - %Lf
    long double ld = 483836821992.3838;
    printf("Long Double - %Lf\n", ld);

    return 0;
}
```

---

## Output

```
Float - 549.560059
Double - 489273883.770000
Long Double - 483836821992.383789
```

> 🔍 লক্ষ্য করো: `float` এ দেওয়া `549.56` প্রিন্ট
> হয়েছে `549.560059` — এটা **precision error**।
> `float`-এর নির্ভুলতা সীমিত বলেই এটা হয়।
> `double` ব্যবহার করলে এই সমস্যা অনেক কমে।

---

## সাইজ যাচাই করা

```c
#include <stdio.h>

int main()
{
    printf("float size      : %zu bytes\n", sizeof(float));
    printf("double size     : %zu bytes\n", sizeof(double));
    printf("long double size: %zu bytes\n", sizeof(long double));

    return 0;
}
```

**Output (সাধারণত):**

```
float size      : 4 bytes
double size     : 8 bytes
long double size: 12 bytes
```

---

## কোনটা কখন ব্যবহার করবে?

| পরিস্থিতি                         | ব্যবহার করো   |
|------------------------------------|---------------|
| সাধারণ দশমিক হিসাব                | `double`      |
| Memory বাঁচাতে হবে (যেমন game)    | `float`       |
| অনেক বেশি নির্ভুলতা দরকার         | `long double` |

> 💡 **সহজ নিয়ম:** সন্দেহ হলে `double` ব্যবহার
> করো। এটা সবচেয়ে নিরাপদ choice।

---

## Format Specifier চিটশিট

| Type          | printf  | scanf   |
|---------------|---------|---------|
| `float`       | `%f`    | `%f`    |
| `double`      | `%f`    | `%lf`   |
| `long double` | `%Lf`   | `%Lf`   |

> ⚠️ **মজার তথ্য:** `printf`-এ `double` এর জন্য
> `%f` ব্যবহার করা যায়। কিন্তু `scanf`-এ
> অবশ্যই `%lf` লিখতে হবে। এই পার্থক্যটা
> মাথায় রেখো!

---

## সংক্ষেপে মনে রাখো

```
float       → 4 bytes  → %f  → দশমিক ঘর ~6
double      → 8 bytes  → %lf → দশমিক ঘর ~15
long double → 12 bytes → %Lf → দশমিক ঘর ~18
```

---

## পরের Lesson-এ কী আসবে?

**Lesson 12** — `char` Data Type: কিভাবে C-তে
একটা character store করা যায়, এবং কেন char
আসলে integer-এর মতোই কাজ করে।

---

*📁 এই lesson-টি `lesson-11-float-double-longdouble.md`
নামে save করো।*