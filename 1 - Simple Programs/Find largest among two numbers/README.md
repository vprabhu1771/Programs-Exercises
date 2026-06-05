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
