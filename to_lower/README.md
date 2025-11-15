```
#include <stdio.h>

char to_lower(char data);

int main()
{
    printf("%c", to_lower('1'));

    return 0;
}

char to_lower(char data)
{
    if(data >= 65 && data <= 90) 
    {
        return data + 32;    
    }
    else
    {
        return data;
    }
    
}
```