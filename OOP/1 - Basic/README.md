Your C program stores two dates of birth using a structure and prints them.

### C Program Using Structure

```c
#include <stdio.h>

struct date_of_birth
{
    int date;
    int month;
    int year;
};

int main()
{
    struct date_of_birth abi, ram;

    abi.date = 3;
    abi.month = 8;
    abi.year = 1992;

    ram.date = 23;
    ram.month = 3;
    ram.year = 1990;

    printf("%d-%d-%d\n", abi.date, abi.month, abi.year);
    printf("%d-%d-%d\n", ram.date, ram.month, ram.year);

    return 0;
}
```

### Output

```text
3-8-1992
23-3-1990
```

### Alternative: Structure Initialization

```c
#include <stdio.h>

struct date_of_birth
{
    int date;
    int month;
    int year;
};

int main()
{
    struct date_of_birth abi = {3, 8, 1992};
    struct date_of_birth ram = {23, 3, 1990};

    printf("%d-%d-%d\n", abi.date, abi.month, abi.year);
    printf("%d-%d-%d\n", ram.date, ram.month, ram.year);

    return 0;
}
```

**Topic:** Structure in C (User-defined Data Type)
**Structure Name:** `date_of_birth`
**Structure Members:** `date`, `month`, `year`
**Objects:** `abi`, `ram`

### C++ Version

```cpp
#include <iostream>
using namespace std;

struct DateOfBirth
{
    int date;
    int month;
    int year;
};

int main()
{
    DateOfBirth abi, ram;

    abi.date = 3;
    abi.month = 8;
    abi.year = 1992;

    ram.date = 23;
    ram.month = 3;
    ram.year = 1990;

    cout << abi.date << "-" << abi.month << "-" << abi.year << endl;
    cout << ram.date << "-" << ram.month << "-" << ram.year << endl;

    return 0;
}
```

### C++ Version Using Class

```cpp
#include <iostream>
using namespace std;

class DateOfBirth
{
private:
    int date;
    int month;
    int year;

public:
    void setData(int d, int m, int y)
    {
        date = d;
        month = m;
        year = y;
    }

    void display()
    {
        cout << date << "-" << month << "-" << year << endl;
    }
};

int main()
{
    DateOfBirth abi, ram;

    abi.setData(3, 8, 1992);
    ram.setData(23, 3, 1990);

    abi.display();
    ram.display();

    return 0;
}
```

### Output

```text
3-8-1992
23-3-1990
```

### Constructor Version (Better Approach)

```cpp
#include <iostream>
using namespace std;

class DateOfBirth
{
private:
    int date;
    int month;
    int year;

public:
    DateOfBirth(int d, int m, int y)
    {
        date = d;
        month = m;
        year = y;
    }

    void display()
    {
        cout << date << "-" << month << "-" << year << endl;
    }
};

int main()
{
    DateOfBirth abi(3, 8, 1992);
    DateOfBirth ram(23, 3, 1990);

    abi.display();
    ram.display();

    return 0;
}
```

This class version demonstrates **data members**, **member functions**, **object creation**, and optionally **constructors**.


### Java Version

```java
class DateOfBirth {
    int date;
    int month;
    int year;
}

public class Main {
    public static void main(String[] args) {

        DateOfBirth abi = new DateOfBirth();
        DateOfBirth ram = new DateOfBirth();

        abi.date = 3;
        abi.month = 8;
        abi.year = 1992;

        ram.date = 23;
        ram.month = 3;
        ram.year = 1990;

        System.out.println(abi.date + "-" + abi.month + "-" + abi.year);
        System.out.println(ram.date + "-" + ram.month + "-" + ram.year);
    }
}
```

### Python Version

```python
class DateOfBirth:
    def __init__(self, date, month, year):
        self.date = date
        self.month = month
        self.year = year

abi = DateOfBirth(3, 8, 1992)
ram = DateOfBirth(23, 3, 1990)

print(f"{abi.date}-{abi.month}-{abi.year}")
print(f"{ram.date}-{ram.month}-{ram.year}")
```

### Output

```
3-8-1992
23-3-1990
```

**Note:** In your C code, the second `printf()` should use `ram.date`, `ram.month`, and `ram.year` instead of `abi.date`, `abi.month`, and `abi.year`:

```c
printf("%d - %d - %d\n", ram.date, ram.month, ram.year);
```

Also replace the curly quotes (`“ ”`) with normal double quotes (`" "`).
