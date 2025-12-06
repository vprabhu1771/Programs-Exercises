Here is your **Add Two Complex Numbers** program — fully corrected, formatted, and provided in both **C** and **C++**.

Your logic is correct.
I fixed:
✔ `void main()` → `int main()` (standard C)
✔ formatting and printing style

---

# ✅ Corrected **C Program**

```c
#include <stdio.h>

typedef struct complex {
    float real;
    float imag;
} complex;

complex add(complex n1, complex n2);

int main() {
    complex n1, n2, temp;

    printf("For 1st complex number\n");
    printf("Enter real and imaginary parts:\n");
    scanf("%f %f", &n1.real, &n1.imag);

    printf("\nFor 2nd complex number\n");
    printf("Enter real and imaginary parts:\n");
    scanf("%f %f", &n2.real, &n2.imag);

    temp = add(n1, n2);

    if (temp.imag >= 0)
        printf("Sum = %.1f + %.1fi\n", temp.real, temp.imag);
    else
        printf("Sum = %.1f - %.1fi\n", temp.real, -temp.imag);

    return 0;
}

complex add(complex n1, complex n2) {
    complex temp;
    temp.real = n1.real + n2.real;
    temp.imag = n1.imag + n2.imag;
    return temp;
}
```

---

# ✅ Corrected **C++ Program**

```cpp
#include <iostream>
using namespace std;

struct complex {
    float real;
    float imag;
};

complex add(complex n1, complex n2) {
    complex temp;
    temp.real = n1.real + n2.real;
    temp.imag = n1.imag + n2.imag;
    return temp;
}

int main() {
    complex n1, n2, temp;

    cout << "For 1st complex number\n";
    cout << "Enter real and imaginary parts:\n";
    cin >> n1.real >> n1.imag;

    cout << "\nFor 2nd complex number\n";
    cout << "Enter real and imaginary parts:\n";
    cin >> n2.real >> n2.imag;

    temp = add(n1, n2);

    if (temp.imag >= 0)
        cout << "Sum = " << temp.real << " + " << temp.imag << "i\n";
    else
        cout << "Sum = " << temp.real << " - " << -temp.imag << "i\n";

    return 0;
}
```

---

### 📌 Example Output

```
For 1st complex number
Enter real and imaginary parts:
3 4

For 2nd complex number
Enter real and imaginary parts:
5 7
Sum = 8.0 + 11.0i
```

---

If you want, I can also provide:
✔ Complex number subtraction
✔ Multiplication and division
✔ Using functions with pointers
✔ Menu-driven program (Add/Subtract/Mul)

Would you like those versions too?
