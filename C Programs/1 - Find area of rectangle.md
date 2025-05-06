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

# Java

```java
import java.util.Scanner;

public class RectangleArea {
    public static void main(String[] args) {
        int length, breadth, area;

        Scanner scanner = new Scanner(System.in);

        // Input from user
        System.out.println("Enter Length of Rectangle:");
        length = scanner.nextInt();

        System.out.println("Enter Breadth of Rectangle:");
        breadth = scanner.nextInt();

        // Calculate area
        area = length * breadth;

        // Output results
        System.out.println("Area of Rectangle " + (length * breadth));
        System.out.println("Area of Rectangle " + area);

        scanner.close();
    }
}
```

# Python

```python
# Input from user
length = int(input("Enter Length of Rectangle: "))
breadth = int(input("Enter Breadth of Rectangle: "))

# Calculate area
area = length * breadth

# Output results
print("Area of Rectangle", length * breadth)
print("Area of Rectangle", area)
```
