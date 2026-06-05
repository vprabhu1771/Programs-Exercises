# C
```c
#include<stdio.h>

int main()
{
    int a, b;

    printf("Enter a\n");

    scanf("%d", &a);

    printf("Enter b\n");

    scanf("%d", &b);

     // Using ternary operator
    (a > b) ? printf("a = %d is Maximum\n", a)
            : printf("b = %d is Maximum\n", b);

    // OR

    if(a > b)
    {
        printf("a = %d is Maximum\n", a);
    }
    else
    {
        printf("b = %d is maximum\n", b);
    }
    
    return 0;
}
```
# CPP
```cpp
#include<iostream.h>

using namespace std;

int main()
{
    int a, b;

    cout << "Enter a\n";

    cin >> a;

    cout << "Enter b\n";

    cin >> b;

     // Using ternary operator
    (a > b) ? cout << "a = " << a << "is Maximum\n" 
            : cout << "b = " << b << "is Maximum\n";

    // OR

    if(a > b)
    {
        cout << "a = " << a << "is Maximum\n";
    }
    else
    {
        cout << "b = " << b << "is Maximum\n";
    }
    
    return 0;
}
```

Here are equivalent **Java** and **Python** versions of your C program.

## Java

```java
import java.util.Scanner;

public class MaximumNumber {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.println("Enter a");
        int a = sc.nextInt();

        System.out.println("Enter b");
        int b = sc.nextInt();

        // Using ternary operator
        System.out.println((a > b)
                ? "a = " + a + " is Maximum"
                : "b = " + b + " is Maximum");

        // OR

        if (a > b) {
            System.out.println("a = " + a + " is Maximum");
        } else {
            System.out.println("b = " + b + " is Maximum");
        }

        sc.close();
    }
}
```

---

## Python

```python
a = int(input("Enter a: "))
b = int(input("Enter b: "))

# Using ternary operator
print(f"a = {a} is Maximum" if a > b else f"b = {b} is Maximum")

# OR

if a > b:
    print(f"a = {a} is Maximum")
else:
    print(f"b = {b} is Maximum")
```

---

### Handling Equal Values

If you want to correctly handle the case when `a` and `b` are equal:

#### Java

```java
if (a > b) {
    System.out.println("a = " + a + " is Maximum");
} else if (b > a) {
    System.out.println("b = " + b + " is Maximum");
} else {
    System.out.println("Both numbers are equal: " + a);
}
```

#### Python

```python
if a > b:
    print(f"a = {a} is Maximum")
elif b > a:
    print(f"b = {b} is Maximum")
else:
    print(f"Both numbers are equal: {a}")
```

A small difference from C: in Python, the ternary operator is written as:

```python
value_if_true if condition else value_if_false
```

while in C and Java it is:

```c
condition ? value_if_true : value_if_false
```
