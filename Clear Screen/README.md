# c
```c
#include <stdio.h>
#include <stdlib.h>

int main() {

    #ifdef _WIN32
        system("cls");
    #else
        system("clear");
    #endif

  return 0;
}
```
