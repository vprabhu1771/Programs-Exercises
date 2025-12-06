Below is a **fully corrected** and **properly formatted** program for *Polynomial Addition using Structures and Functions* in both **C** and **C++**.

Your code had:
✔ Logic correct
❌ But formatting errors
❌ Function declaration wrong format
❌ `clrscr()` not standard
❌ Return type mismatch in `print_addpolynomial`

---

# ✅ Corrected **C Program**

```c
#include <stdio.h>
#define MAX 20

struct addpolynomial {
    int exp, coef;
};

// Function to read polynomial
int read_addpolynomial(struct addpolynomial p[]) {
    int i = 0, texp;
    printf("\nEnter exponent (-1 to stop): ");
    scanf("%d", &texp);

    while (texp != -1) {
        p[i].exp = texp;
        printf("Enter coefficient: ");
        scanf("%d", &p[i].coef);
        i++;

        printf("\nEnter exponent (-1 to stop): ");
        scanf("%d", &texp);
    }
    return i;
}

// Function to print polynomial
void print_addpolynomial(struct addpolynomial p[], int max1) {
    int i;
    for (i = 0; i < max1; i++)
        printf("%+dX^%d ", p[i].coef, p[i].exp);
}

// Function to add polynomials
int add_addpolynomial(struct addpolynomial p1[], struct addpolynomial p2[],
                      struct addpolynomial p3[], int max1, int max2) 
{
    int i = 0, j = 0, k = 0;

    while (i < max1 && j < max2) {
        if (p1[i].exp > p2[j].exp) {
            p3[k] = p1[i];
            i++; k++;
        }
        else if (p1[i].exp < p2[j].exp) {
            p3[k] = p2[j];
            j++; k++;
        }
        else {
            p3[k].exp = p1[i].exp;
            p3[k].coef = p1[i].coef + p2[j].coef;
            i++; j++; k++;
        }
    }

    while (i < max1) p3[k++] = p1[i++];
    while (j < max2) p3[k++] = p2[j++];

    return k;
}

int main() {
    struct addpolynomial p1[MAX], p2[MAX], p3[MAX];
    int max1, max2, max3;

    printf("\nEnter first Polynomial:");
    max1 = read_addpolynomial(p1);

    printf("\nEnter second Polynomial:");
    max2 = read_addpolynomial(p2);

    max3 = add_addpolynomial(p1, p2, p3, max1, max2);

    printf("\n\nFirst Polynomial: ");
    print_addpolynomial(p1, max1);

    printf("\nSecond Polynomial: ");
    print_addpolynomial(p2, max2);

    printf("\nResultant Polynomial: ");
    print_addpolynomial(p3, max3);

    return 0;
}
```

---

# ✅ Corrected **C++ Program**

```cpp
#include <iostream>
using namespace std;
#define MAX 20

struct addpolynomial {
    int exp, coef;
};

int read_addpolynomial(addpolynomial p[]) {
    int i = 0, texp;
    cout << "\nEnter exponent (-1 to stop): ";
    cin >> texp;

    while (texp != -1) {
        p[i].exp = texp;
        cout << "Enter coefficient: ";
        cin >> p[i].coef;
        i++;
        cout << "\nEnter exponent (-1 to stop): ";
        cin >> texp;
    }
    return i;
}

void print_addpolynomial(addpolynomial p[], int max1) {
    for (int i = 0; i < max1; i++)
        cout << (p[i].coef >= 0 ? "+" : "") << p[i].coef 
             << "X^" << p[i].exp << " ";
}

int add_addpolynomial(addpolynomial p1[], addpolynomial p2[],
                      addpolynomial p3[], int max1, int max2) 
{
    int i = 0, j = 0, k = 0;

    while (i < max1 && j < max2) {
        if (p1[i].exp > p2[j].exp) p3[k++] = p1[i++];
        else if (p1[i].exp < p2[j].exp) p3[k++] = p2[j++];
        else {
            p3[k].exp = p1[i].exp;
            p3[k].coef = p1[i].coef + p2[j].coef;
            i++; j++; k++;
        }
    }

    while (i < max1) p3[k++] = p1[i++];
    while (j < max2) p3[k++] = p2[j++];

    return k;
}

int main() {
    addpolynomial p1[MAX], p2[MAX], p3[MAX];
    int max1, max2, max3;

    cout << "\nEnter first Polynomial:";
    max1 = read_addpolynomial(p1);

    cout << "\nEnter second Polynomial:";
    max2 = read_addpolynomial(p2);

    max3 = add_addpolynomial(p1, p2, p3, max1, max2);

    cout << "\n\nFirst Polynomial: ";
    print_addpolynomial(p1, max1);

    cout << "\nSecond Polynomial: ";
    print_addpolynomial(p2, max2);

    cout << "\nResultant Polynomial: ";
    print_addpolynomial(p3, max3);

    return 0;
}
```

---

### 📌 Output Example

```
Enter first Polynomial:
Enter exponent (-1 to stop): 3
Enter coefficient: 5
Enter exponent (-1 to stop): 1
Enter coefficient: 2
Enter exponent (-1 to stop): -1

Enter second Polynomial:
Enter exponent (-1 to stop): 3
Enter coefficient: 4
Enter exponent (-1 to stop): 0
Enter coefficient: 7
Enter exponent (-1 to stop): -1

First Polynomial: +5X^3 +2X^1 
Second Polynomial: +4X^3 +7X^0
Resultant Polynomial: +9X^3 +2X^1 +7X^0
```

---

If you want, I can also provide:
✔ Polynomial Subtraction
✔ Polynomial Multiplication
✔ Display terms in descending/ascending order
✔ Validation for duplicate exponents

Would you like those versions too?
