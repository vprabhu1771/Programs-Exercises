`ctype.h` is a C standard library header file used for **character testing and character conversion**.

## Character Testing Functions

| Function      | Description                                |
| ------------- | ------------------------------------------ |
| `isalnum(c)`  | Checks if character is alphabet or digit   |
| `isalpha(c)`  | Checks if character is alphabet            |
| `isdigit(c)`  | Checks if character is a digit (0-9)       |
| `islower(c)`  | Checks if lowercase letter                 |
| `isupper(c)`  | Checks if uppercase letter                 |
| `isspace(c)`  | Checks if whitespace character             |
| `isblank(c)`  | Checks if space or tab                     |
| `ispunct(c)`  | Checks if punctuation character            |
| `iscntrl(c)`  | Checks if control character                |
| `isprint(c)`  | Checks if printable character              |
| `isgraph(c)`  | Checks if printable character except space |
| `isxdigit(c)` | Checks if hexadecimal digit                |
| `isascii(c)`* | Checks if ASCII character (non-standard)   |

---

## Character Conversion Functions

| Function     | Description                     |
| ------------ | ------------------------------- |
| `toupper(c)` | Converts lowercase to uppercase |
| `tolower(c)` | Converts uppercase to lowercase |

---

## Examples

### 1. isalpha()

```c
#include <stdio.h>
#include <ctype.h>

int main() {
    char ch = 'A';

    if(isalpha(ch))
        printf("Alphabet");

    return 0;
}
```

Output:

```text
Alphabet
```

---

### 2. isdigit()

```c
char ch = '5';

if(isdigit(ch))
    printf("Digit");
```

Output:

```text
Digit
```

---

### 3. isupper() and islower()

```c
char ch = 'a';

printf("%d\n", islower(ch));
printf("%d\n", isupper(ch));
```

Output:

```text
1
0
```

---

### 4. toupper()

```c
char ch = 'a';

printf("%c", toupper(ch));
```

Output:

```text
A
```

---

### 5. tolower()

```c
char ch = 'Z';

printf("%c", tolower(ch));
```

Output:

```text
z
```

---

### 6. isspace()

```c
char ch = ' ';

if(isspace(ch))
    printf("Whitespace Character");
```

Output:

```text
Whitespace Character
```

---

## Frequently Used `ctype.h` Functions

1. `isalnum()`
2. `isalpha()`
3. `isdigit()`
4. `islower()`
5. `isupper()`
6. `isspace()`
7. `ispunct()`
8. `isprint()`
9. `toupper()`
10. `tolower()`

These functions are commonly used for **input validation, character checking, and string processing** in C programs.
