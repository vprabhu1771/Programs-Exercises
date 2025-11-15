```
#include <stdio.h>

char to_upper(char data);

int main()
{
    printf("%c", to_upper('a'));

    return 0;
}

char to_upper(char data)
{
    if(data >= 97 && data <= 122) 
    {
        return data - 32;    
    }
    else
    {
        return data;
    }
    
}
```