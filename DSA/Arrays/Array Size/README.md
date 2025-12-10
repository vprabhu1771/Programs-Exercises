```cpp
#include<iostream>

using namespace std;

#define SIZE 100

int main()
{
    int num[SIZE] = {1,2};

    int n = sizeof(num) / sizeof(num[0]);

    cout<<"no of elements " << n << endl;

    return 0;
}
```

Here is the **fixed and correct explanation + corrected code**.

---

## ✅ **What’s wrong?**

Inside the function:

```cpp
int size(int num[])
```

the parameter `num` **decays to a pointer**, so:

```cpp
sizeof(num)
```

returns the size of a pointer (usually **8 bytes** on 64-bit systems), **not** the size of the array.

Therefore, your function **cannot** determine the array size that way.

---

## ✅ **Correct ways to fix it**

### **Option 1: Use templates (best C++ fix)**

This lets the compiler deduce the array size automatically.

```cpp
#include <iostream>
using namespace std;

template <size_t N>
size_t size(const int (&)[N]) {
    return N;
}

int main() {
    int arr[] = {1, 2, 3, 4, 5};
    cout << "no of elements " << size(arr) << endl;
    return 0;
}
```

✔ Works for any array
✔ No runtime cost
✔ No need to pass size manually

---

### **Option 2: Pass size explicitly (C-style)**

```cpp
#include <iostream>
using namespace std;

int size(int num[], int n) {
    return n;
}

int main() {
    int arr[] = {1,2,3,4,5};
    int n = sizeof(arr) / sizeof(arr[0]);

    cout << "no of elements " << size(arr, n) << endl;
    return 0;
}
```

✔ Works in plain C
❌ Requires caller to compute size manually

---

### **Option 3: Use std::size (C++17)**

```cpp
#include <iostream>
#include <iterator>
using namespace std;

int main() {
    int arr[] = {1,2,3,4,5};

    cout << "no of elements " << std::size(arr) << endl;

    return 0;
}
```

---

## ⭐ **Recommended Fix (Template version)** — most idiomatic C++

```cpp
#include<iostream>
using namespace std;

template <size_t N>
size_t size(const int (&)[N]) {
    return N;
}

int main() {
    int arr[] = {1,2,3,4,5};
    cout << "no of elements " << size(arr) << endl;
    return 0;
}
```

---

If you want, I can also explain *why array parameters decay into pointers* or how to write a generic version for any type.