```
#include <stdio.h>

int is_upper(char data);

int main()
{
    printf("%d", is_upper('A'));

    return 0;
}

int is_upper(char data)
{
    if(data >= 65 && data <= 90)
    {
        return 1;
    }
    else
    {
        return -1;
    }
}
```
