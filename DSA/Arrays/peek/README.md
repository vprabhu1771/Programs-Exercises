```c
#include<stdio.h>

int main()
{    
    int arr[] = {10,20,30,40,50};

    int n = sizeof(arr) / sizeof(arr[0]);

    printf("%d", arr[n-1]);

    return 0;
}
```
