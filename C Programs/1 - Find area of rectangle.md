# C

```c
#include<stdio.h>

#include<conio.h>

void main()
{
	int length, breadth, area;

	clrscr();

	printf("Enter Length of Rectangle\n");

	scanf("%d", &length);

	printf("Enter Breadth of Rectangle\n");

	scanf("%d", &breadth);

	printf("Area of Rectangle %d\n", length * breadth);

	area =  length * breadth;

	printf("Area of Rectangle %d\n", area);	

	getch();
}
```
# CPP

```cpp
#include <iostream>
using namespace std;

int main() {
    int length, breadth, area;

    // Input from user
    cout << "Enter Length of Rectangle" << endl;
    cin >> length;

    cout << "Enter Breadth of Rectangle" << endl;
    cin >> breadth;

    // Calculate area
    area = length * breadth;

    // Output results
    cout << "Area of Rectangle " << (length * breadth) << endl;
    cout << "Area of Rectangle " << area << endl;

    return 0;
}
```
