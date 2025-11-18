# C

```c
#include<stdio.h>

int main()
{
    char data;
    
    printf("Enter an alphabet");
    
    scanf("%c", &data);
    
    if(data == 'a' || 
       data == 'A' || 
       data == 'e' || 
       data == 'E' || 
       data == 'i' || 
       data == 'I' ||
       data == 'o' ||
       data == 'O' ||
       data == 'u' ||
       data == 'U')
   {
       printf("%c is a vowel", data);
   }
   else
   {
       printf("%c is a consonant", data);
   }
    
    return 0;
}
```

# CPP

```cpp
#include<iostream>

using namespace std;

int main()
{
    char data;
    
    cout << "Enter an alphabet" <<endl;
    
    cin >> data;
    
    if(data == 'a' || 
       data == 'A' || 
       data == 'e' || 
       data == 'E' || 
       data == 'i' || 
       data == 'I' ||
       data == 'o' ||
       data == 'O' ||
       data == 'u' ||
       data == 'U')
   {       
        cout << data << " is a vowel" << endl;
   }
   else
   {       
        cout << data << " is a consonant" << endl;
   }
    
    return 0;
}
```
