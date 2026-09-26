# C Programming — Type Conversion

এই lesson-এ C Programming-এর **Type Conversion** বা এক data type-এর value অন্য data type-এ convert করার বিষয়টি শেখানো হয়েছে।

## 1. Character থেকে Integer

```c
char ch = 'T';
int r = ch + 100;

printf("Result: %d\n", r);
```

C-তে `char` arithmetic operation-এ ব্যবহার করলে তার character code ব্যবহার করা হয়।

ASCII অনুযায়ী:

```text
'T' = 84
84 + 100 = 184
```

তাই output:

```text
Result: 184
```

## 2. `%c`, `%d`, `%x` দিয়ে Character দেখা

```c
printf("%c %d %x\n", ch, ch, ch);
```

- `%c` → character
- `%d` → decimal integer
- `%x` → hexadecimal integer

`T`-এর ASCII value `84`, আর `84` hexadecimal-এ `54`।

Output:

```text
T 84 54
```

## 3. Integer থেকে Float Conversion

```c
int r = 184;
float f = (float)r;

printf("Float: %f\n", f);
```

এখানে `(float)r` হলো **explicit type casting**।

```text
184 → 184.000000
```

একই কাজ সরাসরি করা যায়:

```c
printf("Float: %f\n", (float)r);
```

## 4. Type Casting কী?

একটি value-কে নির্দিষ্ট data type হিসেবে ব্যবহার করাকে type casting বলা হয়।

Syntax:

```c
(type)value
```

উদাহরণ:

```c
int x = 10;
float y = (float)x;
```

অথবা:

```c
float x = 10.5f;
int y = (int)x;
```

এখানে `y` হবে `10`।

## 5. Float থেকে Integer

```c
float a = 6.6f;
float b = 8.8f;
float c = 7.9f;

int result = a + b + c;
```

প্রথমে যোগ হবে:

```text
6.6 + 8.8 + 7.9 = 23.3
```

তারপর `23.3` integer variable-এ রাখা হবে:

```text
23
```

এটি **implicit conversion**।

## 6. Implicit Type Conversion

যখন programmer নিজে cast না লিখলেও C প্রয়োজন অনুযায়ী conversion করে, সেটি implicit conversion।

```c
float x = 10.5f;
int y = x;
```

এখানে `(int)` লেখা হয়নি, কিন্তু `x`-কে `int`-এ convert করে `y`-তে রাখা হবে।

## 7. প্রতিটি Float আগে Convert করলে

```c
int result2 = (int)a + (int)b + (int)c;
```

এখানে প্রতিটি value আলাদাভাবে convert হবে:

```text
(int)6.6 = 6
(int)8.8 = 8
(int)7.9 = 7

6 + 8 + 7 = 21
```

তাই `result2` হবে:

```text
21
```

## 8. সবচেয়ে গুরুত্বপূর্ণ পার্থক্য

এই দুইটি একই নয়:

```c
int result = a + b + c;
```

এখানে:

```text
6.6 + 8.8 + 7.9 = 23.3
23.3 → 23
```

অন্যদিকে:

```c
int result2 = (int)a + (int)b + (int)c;
```

এখানে:

```text
6.6 → 6
8.8 → 8
7.9 → 7

6 + 8 + 7 = 21
```

**অর্থাৎ conversion কখন হচ্ছে সেটি গুরুত্বপূর্ণ।**

## 9. Float থেকে Int করলে Rounding হয় না

```c
(int)6.9
```

ফল:

```text
6
```

এটি `7` হবে না।

আর:

```c
(int)-6.9
```

ফল:

```text
-6
```

সাধারণভাবে fractional অংশ বাদ দিয়ে zero-এর দিকে conversion হয়।

## 10. `f` কেন ব্যবহার করা হয়েছে?

```c
float a = 6.6f;
```

`f` দিয়ে বোঝানো হয় যে floating-point literal-টি `float` হিসেবে ব্যবহার করা হবে।

```c
6.6
```

সাধারণত `double` literal, আর:

```c
6.6f
```

`float` literal।

## 11. Explicit vs Implicit

### Explicit

Programmer নিজে conversion নির্দেশ করে:

```c
int y = (int)x;
```

### Implicit

Compiler প্রয়োজন অনুযায়ী conversion করে:

```c
int y = x;
```

## 12. সম্পূর্ণ Corrected Code

Original code-এ `Total (No Conversation)` লেখা ছিল। এখানে সেটিকে `Total (No Conversion)` করা হয়েছে।

```c
#include <stdio.h>

int main()
{
    char ch = 'T';
    int r = ch + 100;

    printf("Result: %d\n", r);
    printf("%c %d %x\n", ch, ch, ch);

    float f = (float)r;
    printf("Float: %f\n", f);
    printf("Float: %f\n", (float)r);

    float a = 6.6f;
    float b = 8.8f;
    float c = 7.9f;

    int result = a + b + c;
    printf("Total (No Conversion): %d\n", result);

    int result2 = (int)a + (int)b + (int)c;
    printf("Total: %d\n", result2);

    return 0;
}
```

## 13. সম্ভাব্য Output

```text
Result: 184
T 84 54
Float: 184.000000
Float: 184.000000
Total (No Conversion): 23
Total: 21
```

## 14. Common Mistakes

### ভুল ১: Float থেকে Int করলে rounding হবে ভাবা

```text
8.9 → 8
```

সাধারণ cast-এ `9` হবে না।

### ভুল ২: Conversion-এর অবস্থানকে গুরুত্ব না দেওয়া

```c
(int)(a + b + c)
```

এবং:

```c
(int)a + (int)b + (int)c
```

একই result নাও দিতে পারে।

### ভুল ৩: Float `%d` দিয়ে print করা

ভুল:

```c
float x = 10.5f;
printf("%d", x);
```

সঠিক:

```c
printf("%f", x);
```

### ভুল ৪: `%c` এবং `%d` গুলিয়ে ফেলা

```c
char ch = 'A';

printf("%c\n", ch);
printf("%d\n", ch);
```

Output:

```text
A
65
```

## 15. Practice

```c
#include <stdio.h>

int main()
{
    float a = 9.8f;
    float b = 2.4f;

    int x = a + b;
    int y = (int)a + (int)b;

    printf("x = %d\n", x);
    printf("y = %d\n", y);

    return 0;
}
```

নিজে আগে অনুমান করুন:

```text
a + b = ?
x = ?
y = ?
```

## 16. Mini Challenge

একটি program লিখুন যেখানে:

1. একটি `char` variable থাকবে।
2. তার numeric value print করবেন।
3. একটি `int` value-কে `float`-এ convert করবেন।
4. তিনটি `float` value নেবেন।
5. আগে তাদের যোগ করে `int`-এ রাখবেন।
6. এরপর প্রতিটি float-কে আলাদাভাবে `int`-এ cast করে যোগ করবেন।
7. দুই result compare করবেন।

## Quick Revision

```text
Type Conversion
├── Implicit Conversion
│   └── Compiler নিজে conversion করে
│
└── Explicit Conversion
    └── Programmer নিজে cast করে
```

Type casting syntax:

```c
(type)value
```

উদাহরণ:

```c
(int)10.5
(float)10
```

সবচেয়ে গুরুত্বপূর্ণ:

```c
(int)(6.6 + 8.8 + 7.9)
```

এখানে:

```text
23.3 → 23
```

কিন্তু:

```c
(int)6.6 + (int)8.8 + (int)7.9
```

এখানে:

```text
6 + 8 + 7 = 21
```

**Conversion-এর সময় ও অবস্থান result পরিবর্তন করতে পারে।**

## Conclusion

এই lesson থেকে শিখলাম:

- `char`-এর numeric character code ব্যবহার করা যায়।
- `%c`, `%d`, `%x` দিয়ে value বিভিন্ন format-এ দেখা যায়।
- `int` থেকে `float` conversion করা যায়।
- `float` থেকে `int` conversion করলে fractional অংশ বাদ যায়।
- Explicit conversion-এর জন্য `(type)` syntax ব্যবহার করা হয়।
- C প্রয়োজন হলে implicit conversion করতে পারে।
- Conversion কখন হচ্ছে সেটি result-এর ওপর গুরুত্বপূর্ণ প্রভাব ফেলতে পারে।
