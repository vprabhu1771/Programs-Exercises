```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define size 100

int main() {

    char name[size];
    int age;

    FILE *file = fopen("example.txt", "a");
    
    #ifdef _WIN32
        system("cls");
    #else
        system("clear");
    #endif

    printf("Enter your name: ");
    scanf("%99s", name);

    printf("Enter your age: ");
    scanf("%d", &age);

    if (file == NULL) {
        printf("Error creating file.\n");
        return 1;
    }

    fprintf(file, "\nname\t:\t%s\n", name);
    fprintf(file, "age\t:\t%d\n", age);

    fclose(file);

    printf("Data written successfully.\n");
    return 0;
}
```
