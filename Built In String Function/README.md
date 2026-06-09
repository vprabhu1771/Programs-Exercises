`string.h` is a C standard library header that provides functions for string handling and memory manipulation.

## String Functions

| Function     | Description                                       |
| ------------ | ------------------------------------------------- |
| `strlen()`   | Returns length of a string                        |
| `strcpy()`   | Copies one string to another                      |
| `strncpy()`  | Copies specified number of characters             |
| `strcat()`   | Concatenates (joins) two strings                  |
| `strncat()`  | Concatenates specified number of characters       |
| `strcmp()`   | Compares two strings                              |
| `strncmp()`  | Compares first n characters of two strings        |
| `strchr()`   | Finds first occurrence of a character             |
| `strrchr()`  | Finds last occurrence of a character              |
| `strstr()`   | Finds a substring in a string                     |
| `strtok()`   | Splits string into tokens                         |
| `strspn()`   | Returns length of initial matching characters     |
| `strcspn()`  | Returns length of initial non-matching characters |
| `strpbrk()`  | Finds first matching character from a set         |
| `strcoll()`  | Compares strings according to locale              |
| `strxfrm()`  | Transforms string for locale comparison           |
| `strerror()` | Returns error message string                      |

---

## Memory Functions

| Function    | Description                     |
| ----------- | ------------------------------- |
| `memcpy()`  | Copies memory block             |
| `memmove()` | Copies memory block safely      |
| `memset()`  | Fills memory with a value       |
| `memcmp()`  | Compares memory blocks          |
| `memchr()`  | Searches memory for a character |

---

## Commonly Used Examples

### 1. strlen()

```c
#include <stdio.h>
#include <string.h>

int main() {
    char str[] = "Hello";
    printf("Length = %d", strlen(str));
    return 0;
}
```

Output:

```
Length = 5
```

### 2. strcpy()

```c
char source[] = "OpenAI";
char destination[20];

strcpy(destination, source);
```

### 3. strcat()

```c
char str1[20] = "Hello ";
char str2[] = "World";

strcat(str1, str2);
printf("%s", str1);
```

Output:

```
Hello World
```

### 4. strcmp()

```c
char str1[] = "ABC";
char str2[] = "ABC";

if(strcmp(str1, str2) == 0)
    printf("Equal");
```

Output:

```
Equal
```

### 5. strstr()

```c
char str[] = "I am a good person";

if(strstr(str, "good"))
    printf("Found");
```

Output:

```
Found
```

## Frequently Asked `string.h` Functions for Exams

1. `strlen()`
2. `strcpy()`
3. `strncpy()`
4. `strcat()`
5. `strncat()`
6. `strcmp()`
7. `strncmp()`
8. `strchr()`
9. `strrchr()`
10. `strstr()`
11. `strtok()`
12. `memcpy()`
13. `memmove()`
14. `memset()`
15. `memcmp()`

These are the most important `string.h` functions commonly used in C programming and interview questions.
