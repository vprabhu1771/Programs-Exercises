```
#include <stdio.h>

int is_space(char data);

int main()
{
    printf("%d", is_space(' '));

    return 0;
}

int is_space(char data)
{
    if(data == 32)
    {
        return 1;
    }
    else
    {
        return -1;
    }
}
```
