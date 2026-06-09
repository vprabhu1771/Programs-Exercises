## Find Area of Circle

### Formula

genui{"math_block_widget_always_prefetch_v2":{"content":"A=\pi r^2"}}

Where:

* `A` = Area of Circle
* `r` = Radius
* `π ≈ 3.14159`

---

## C

```c
#include <stdio.h>

int main()
{
    float radius, area;

    printf("Enter Radius of Circle\n");
    scanf("%f", &radius);

    area = 3.14159 * radius * radius;

    printf("Area of Circle %.2f\n", area);

    return 0;
}
```

---

## C++

```cpp
#include <iostream>
using namespace std;

int main()
{
    float radius, area;

    cout << "Enter Radius of Circle" << endl;
    cin >> radius;

    area = 3.14159 * radius * radius;

    cout << "Area of Circle " << area << endl;

    return 0;
}
```

---

## Java

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        double radius, area;

        System.out.println("Enter Radius of Circle");
        radius = sc.nextDouble();

        area = 3.14159 * radius * radius;

        System.out.println("Area of Circle " + area);

        sc.close();
    }
}
```

---

## Python

```python
radius = float(input("Enter Radius of Circle: "))

area = 3.14159 * radius * radius

print("Area of Circle", area)
```

---

## Output

```text
Enter Radius of Circle
5

Area of Circle 78.53975
```

### Using Math Libraries

* C: `M_PI` from `math.h` (compiler dependent)
* C++: `M_PI` from `<cmath>`
* Java: `Math.PI`
* Python: `math.pi`

Example:

```python
import math

radius = 5
area = math.pi * radius * radius

print(area)
```

Output:

```text
78.53981633974483
```
