# C Programming — String

> এই নোটটি C Programming-এর String অধ্যায়ের beginner-friendly documentation। এখানে String কী, Character ও String-এর পার্থক্য, String declaration, initialization, indexing এবং input নেওয়ার বিষয়গুলো আলোচনা করা হয়েছে।

---

## 1. String কী?

C Programming-এ **String** হলো একাধিক character-এর একটি sequence, যা সাধারণত `char` array-এর মধ্যে রাখা হয়।

উদাহরণ:

```c
"Hello"
```

Memory-তে এটি প্রায় এমনভাবে থাকে:

```text
H  e  l  l  o  \0
```

শেষে থাকা `\0`-কে বলা হয় **Null Character**।

C Programming-এ একটি String কোথায় শেষ হয়েছে তা বোঝানোর জন্য `\0` খুব গুরুত্বপূর্ণ।

---

## 2. Character কী?

একটি মাত্র character রাখার জন্য C-তে `char` data type ব্যবহার করা হয়।

```c
char letter = 'A';
```

এখানে:

- `char` → data type
- `letter` → variable
- `'A'` → একটি character

Character লেখার সময় **single quotation (`' '`)** ব্যবহার করতে হয়।

```c
'A'
'B'
'7'
' '
```

---

## 3. Character এবং String-এর পার্থক্য

### Character

একটি মাত্র character:

```c
char letter = 'A';
```

### String

একাধিক character:

```c
char name[] = "Sahin";
```

String-এর জন্য সাধারণত `char` array ব্যবহার করা হয়।

---

# 4. String কীভাবে কাজ করে?

ধরা যাক:

```c
char name[] = "Sahin";
```

Memory-তে এটি প্রায় এমনভাবে রাখা হয়:

```text
Index:    0    1    2    3    4    5
          ↓    ↓    ↓    ↓    ↓    ↓
Value:   'S'  'a'  'h'  'i'  'n' '\0'
```

অর্থাৎ:

```c
name[0] = 'S';
name[1] = 'a';
name[2] = 'h';
name[3] = 'i';
name[4] = 'n';
name[5] = '\0';
```

String-এর character শুরু হয় **index 0** থেকে।

---

# 5. String-এর শেষে `\0` কেন থাকে?

C-এর String output ও String-related operation বুঝতে পারে String কোথায় শেষ হয়েছে।

উদাহরণ:

```c
char name[] = "Sahin";
```

বাস্তবে:

```text
S a h i n \0
```

যদি `\0` না থাকে, তাহলে C বুঝতে নাও পারে String কোথায় শেষ হয়েছে।

---

# 6. String Declaration

String declare করার একটি উপায়:

```c
char name[20];
```

এখানে:

- `char` → character type
- `name` → variable name
- `[20]` → 20টি `char` রাখার জায়গা

String হিসেবে ব্যবহার করার সময় Null Character-এর জন্যও জায়গা প্রয়োজন।

যেমন:

```c
char name[6] = "Sahin";
```

কারণ:

```text
S a h i n \0
```

মোট 6টি `char` space প্রয়োজন।

---

# 7. String Declaration/Initialization-এর তিনটি পদ্ধতি

## Way 1 — Character আলাদাভাবে assign করা

```c
char bio[90];

bio[0] = 'S';
bio[1] = 'A';
bio[2] = '\0';
```

এখন এটি একটি valid String:

```text
S A \0
```

তারপর:

```c
printf("%s\n", bio);
```

Output:

```text
SA
```

> গুরুত্বপূর্ণ: শুধু `bio[0]` এবং `bio[1]` assign করে `%s` দিয়ে print করা নিরাপদ নয়। Manually String তৈরি করলে শেষে `'\0'` দিতে হবে।

---

## Way 2 — Character দিয়ে Array initialize করা

```c
char name[20] = {'H', 'M', ' ', 'S'};
```

এখানে characterগুলো array-এর মধ্যে রাখা হয়েছে।

Array-এর size 20 হলেও মাত্র 4টি value দেওয়া হয়েছে। বাকি elements zero-initialized হবে।

তারপর:

```c
printf("%s\n", name);
```

ব্যবহার করা যায়।

---

## Way 3 — Direct String Literal ব্যবহার করা

সবচেয়ে সহজ পদ্ধতিগুলোর একটি:

```c
char name1[90] = "Hello! I am Sahin. I want to learn C programming";
```

এখানে C নিজেই String-এর শেষে `'\0'` যোগ করে।

তারপর:

```c
printf("%s\n", name1);
```

দিয়ে পুরো String print করা যায়।

---

# 8. String Literal কী?

Double quotation-এর মধ্যে লেখা text-কে String Literal বলা হয়।

উদাহরণ:

```c
"Hello"
"My name is Sahin"
"I am learning C programming"
```

একটি মাত্র character-এর জন্য single quote:

```c
'A'
```

ব্যবহার করা হয়।

---

# 9. Single Quote এবং Double Quote

এটি খুব গুরুত্বপূর্ণ।

### Character

```c
char letter = 'A';
```

Single quote ব্যবহার হয়।

### String

```c
char name[] = "Sahin";
```

Double quote ব্যবহার হয়।

ভুল:

```c
char letter = "A";
```

সঠিক:

```c
char letter = 'A';
```

আবার String:

```c
char name[] = "Sahin";
```

---

# 10. String Print করার জন্য `%s`

`printf()` দিয়ে String print করতে `%s` format specifier ব্যবহার করা হয়।

```c
char name[] = "Sahin";

printf("%s\n", name);
```

Output:

```text
Sahin
```

---

# 11. Character Print করার জন্য `%c`

একটি নির্দিষ্ট character print করতে `%c` ব্যবহার করা হয়।

```c
char name[] = "Sahin";

printf("%c\n", name[0]);
```

Output:

```text
S
```

আর:

```c
printf("%c\n", name[3]);
```

Output:

```text
i
```

---

# 12. String Indexing

C Programming-এ array এবং String-এর index **0 থেকে শুরু হয়**।

ধরা যাক:

```c
char name[] = "Sahin";
```

তাহলে:

```text
Character:  S    a    h    i    n
Index:      0    1    2    3    4
```

অর্থাৎ:

```c
name[0] // S
name[1] // a
name[2] // h
name[3] // i
name[4] // n
```

---

# 13. নির্দিষ্ট Character Access করা

```c
char name[] = "Sahin";

printf("%c\n", name[0]);
printf("%c\n", name[1]);
printf("%c\n", name[2]);
```

Output:

```text
S
a
h
```

---

# 14. Complete Example

```c
#include <stdio.h>

int main()
{
    // First way
    char bio[90];

    bio[0] = 'S';
    bio[1] = 'A';
    bio[2] = '\0';

    printf("%s\n", bio);

    // Second way
    char name[20] = {'H', 'M', ' ', 'S'};

    printf("%s\n", name);

    // Third way
    char name1[90] = "Hello! I am Sahin. I want to learn C programming";

    printf("%s\n", name1);

    printf("Index 3 = %c\n", name1[3]);
    printf("Index 4 = %c\n", name1[4]);

    return 0;
}
```

---

# 15. Code-এর ব্যাখ্যা

## প্রথম অংশ

```c
char bio[90];
```

90টি `char` রাখার জন্য একটি array তৈরি করা হয়েছে।

তারপর:

```c
bio[0] = 'S';
bio[1] = 'A';
bio[2] = '\0';
```

ফলে:

```text
S A \0
```

String তৈরি হয়েছে।

তারপর:

```c
printf("%s\n", bio);
```

Output:

```text
SA
```

---

## দ্বিতীয় অংশ

```c
char name[20] = {'H', 'M', ' ', 'S'};
```

Character দিয়ে array initialize করা হয়েছে।

তারপর:

```c
printf("%s\n", name);
```

String হিসেবে output করা হয়েছে।

---

## তৃতীয় অংশ

```c
char name1[90] = "Hello! I am Sahin. I want to learn C programming";
```

এখানে সরাসরি String Literal ব্যবহার করা হয়েছে।

C নিজে String-এর শেষে:

```c
'\0'
```

যোগ করে।

---

# 16. Index দিয়ে Character বের করা

String:

```c
char name1[90] = "Hello! I am Sahin. I want to learn C programming";
```

এর প্রথম কয়েকটি character:

```text
Index:      0 1 2 3 4 5
Character:  H e l l o !
```

তাই:

```c
printf("Index 3 = %c\n", name1[3]);
```

Output:

```text
Index 3 = l
```

এবং:

```c
printf("Index 4 = %c\n", name1[4]);
```

Output:

```text
Index 4 = o
```

---

# 17. String-এর Length এবং Array Size

ধরা যাক:

```c
char name[20] = "Sahin";
```

এখানে array-এর capacity:

```text
20
```

কিন্তু visible text:

```text
Sahin
```

এতে 5টি character আছে।

আর Null Character-এর জন্য আরও 1টি জায়গা প্রয়োজন।

তাই `Sahin` String রাখার জন্য minimum:

```text
6
```

টি `char` space প্রয়োজন।

---

# 18. Empty String

একটি Empty String হলো এমন String যার প্রথম character-ই `'\0'`।

উদাহরণ:

```c
char name[20] = "";
```

এটি একটি Empty String।

---

# 19. New Line এবং `\n`

C-তে:

```c
\n
```

একটি escape sequence। এটি নতুন লাইনে যেতে ব্যবহার হয়।

উদাহরণ:

```c
printf("Hello\nSahin");
```

Output:

```text
Hello
Sahin
```

String-এর মধ্যেও ব্যবহার করা যায়:

```c
char text[] = "Hello\nSahin";

printf("%s", text);
```

---

# 20. User Input নেওয়া

User-এর কাছ থেকে String input নেওয়ার একটি সহজ উপায় হলো `scanf()`।

```c
char name[30];

printf("What is your name? ");

scanf("%s", name);

printf("Your name is %s\n", name);
```

User যদি input দেয়:

```text
Sahin
```

Output:

```text
Your name is Sahin
```

---

# 21. `scanf("%s", name)`-এ `&` কেন নেই?

Integer input নেওয়ার সময় সাধারণত:

```c
scanf("%d", &age);
```

লিখি।

কিন্তু String-এর ক্ষেত্রে:

```c
scanf("%s", name);
```

লিখি।

কারণ `name` একটি array এবং expression হিসেবে `name` সাধারণত array-এর প্রথম element-এর address হিসেবে কাজ করে।

তাই:

```c
scanf("%s", name);
```

সঠিক।

---

# 22. `scanf("%s")`-এর সীমাবদ্ধতা

`scanf("%s", name)` সাধারণত **space পর্যন্ত** input নেয়।

যেমন user যদি লেখে:

```text
Sahin Shazi
```

তাহলে:

```c
scanf("%s", name);
```

সাধারণত শুধু:

```text
Sahin
```

নেবে।

কারণ `%s` whitespace/space দেখলে input থামিয়ে দেয়।

---

# 23. Input-এর Array Size ঠিক রাখা

যদি লিখি:

```c
char name[20];

scanf("%s", name);
```

তাহলে user-এর input যেন array-এর capacity-এর বাইরে না যায়, সেটি গুরুত্বপূর্ণ।

আরও নিরাপদভাবে width দেওয়া যায়:

```c
scanf("%19s", name);
```

এতে সর্বোচ্চ 19টি character নেওয়া হবে এবং শেষের `'\0'` রাখার জন্য 1টি জায়গা থাকবে।

---

# 24. এই Lesson থেকে যা শিখলাম

- String কী
- Character কী
- Character এবং String-এর পার্থক্য
- `char` data type
- `char` array
- String Literal
- Null Character `'\0'`
- String declaration
- String initialization
- Character দিয়ে String তৈরি
- String indexing
- Index `0` থেকে শুরু হওয়া
- `%s`
- `%c`
- `printf()`
- `scanf()`
- String input
- Empty String
- `\n`
- String-এর capacity
- String-এর শেষে Null Character-এর প্রয়োজনীয়তা

---

# 25. Common Mistakes

## Mistake 1 — Character-এ Double Quote ব্যবহার

ভুল:

```c
char letter = "A";
```

সঠিক:

```c
char letter = 'A';
```

---

## Mistake 2 — String-এ Single Quote ব্যবহার

ভুল:

```c
char name[] = 'Sahin';
```

সঠিক:

```c
char name[] = "Sahin";
```

---

## Mistake 3 — `\0` ভুলে যাওয়া

যদি manually character assign করি:

```c
char name[20];

name[0] = 'S';
name[1] = 'A';
```

এটি String হিসেবে নিরাপদ নয়।

সঠিক:

```c
name[0] = 'S';
name[1] = 'A';
name[2] = '\0';
```

---

## Mistake 4 — ভুল Format Specifier

String:

```c
printf("%s", name);
```

Character:

```c
printf("%c", name[0]);
```

---

## Mistake 5 — Index ভুল করা

String:

```text
Sahin
```

এর index:

```text
S → 0
a → 1
h → 2
i → 3
n → 4
```

তাই:

```c
name[5]
```

visible character নয়; সেখানে সাধারণত `'\0'` থাকে।

---

# 26. Practice

### Practice 1

একটি String তৈরি করুন:

```text
Hello, C Programming!
```

### Practice 2

একটি String-এর প্রথম character print করুন।

```c
printf("%c", name[0]);
```

### Practice 3

String-এর 3 নম্বর index-এর character print করুন।

### Practice 4

নিজের নাম character by character assign করুন।

```c
char name[20];

name[0] = 'S';
name[1] = 'a';
name[2] = 'h';
name[3] = 'i';
name[4] = 'n';
name[5] = '\0';
```

### Practice 5

`scanf()` ব্যবহার করে user-এর নাম input নিন।

```c
char name[30];

printf("What is your name? ");
scanf("%29s", name);

printf("Hello, %s", name);
```

---

# 27. Challenge

নিজে চেষ্টা করে নিচের output তৈরি করুন:

```text
My name is Sahin
I am learning C
My first character is M
My last character is n
```

প্রথমে solution না দেখে নিজে code লিখুন।

---

# 28. Quick Revision

### Character

```c
char letter = 'A';
```

### String

```c
char name[] = "Sahin";
```

### String print

```c
printf("%s", name);
```

### Character print

```c
printf("%c", name[0]);
```

### String input

```c
scanf("%s", name);
```

### String indexing

```c
name[0]
name[1]
name[2]
```

### Null Character

```c
'\0'
```

### New line

```c
\n
```

---

# Conclusion

C Programming-এ String আলাদা কোনো built-in data type নয়।

String মূলত `char`-এর একটি array, যার শেষে `'\0'` দিয়ে String-এর শেষ নির্দেশ করা হয়।

সবচেয়ে গুরুত্বপূর্ণ তিনটি বিষয় মনে রাখুন:

```text
Character → 'A'
String    → "ABC"
String end → '\0'
```

আর String-এর index শুরু হয়:

```text
0
```

থেকে।

এই ভিত্তি ভালোভাবে বুঝে ফেললে পরবর্তী সময়ে `strlen()`, `strcpy()`, `strcat()`, `strcmp()`, `fgets()` ইত্যাদি শেখা অনেক সহজ হবে।
