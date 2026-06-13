Below are examples of storing and reading a **Date of Birth** from a file using **File I/O** in **C, C++, Java, and Python**, using both **Structure/Class (OOP)** approaches where applicable.

---

# 1. C (Structure + File I/O)

### Write and Read Structure from File

```c
#include <stdio.h>

struct DateOfBirth
{
    int date;
    int month;
    int year;
};

int main()
{
    FILE *fp;
    struct DateOfBirth person;

    person.date = 3;
    person.month = 8;
    person.year = 1992;

    /* Write to file */
    fp = fopen("dob.dat", "wb");
    fwrite(&person, sizeof(person), 1, fp);
    fclose(fp);

    /* Read from file */
    fp = fopen("dob.dat", "rb");
    fread(&person, sizeof(person), 1, fp);
    fclose(fp);

    printf("Date of Birth: %d-%d-%d\n",
           person.date,
           person.month,
           person.year);

    return 0;
}
```

---

# 2. C++ (Class + File I/O)

```cpp
#include <iostream>
#include <fstream>
using namespace std;

class DateOfBirth
{
private:
    int date, month, year;

public:
    void setData(int d, int m, int y)
    {
        date = d;
        month = m;
        year = y;
    }

    void writeFile()
    {
        ofstream fout("dob.txt");
        fout << date << " "
             << month << " "
             << year;
        fout.close();
    }

    void readFile()
    {
        ifstream fin("dob.txt");
        fin >> date >> month >> year;
        fin.close();
    }

    void display()
    {
        cout << "Date of Birth: "
             << date << "-"
             << month << "-"
             << year << endl;
    }
};

int main()
{
    DateOfBirth obj;

    obj.setData(3, 8, 1992);
    obj.writeFile();

    obj.readFile();
    obj.display();

    return 0;
}
```

---

# 3. C++ (Structure + File I/O)

```cpp
#include <iostream>
#include <fstream>
using namespace std;

struct DateOfBirth
{
    int date;
    int month;
    int year;
};

int main()
{
    DateOfBirth person = {3, 8, 1992};

    ofstream fout("dob.txt");
    fout << person.date << " "
         << person.month << " "
         << person.year;
    fout.close();

    ifstream fin("dob.txt");
    fin >> person.date
        >> person.month
        >> person.year;
    fin.close();

    cout << person.date << "-"
         << person.month << "-"
         << person.year << endl;

    return 0;
}
```

---

# 4. Java (OOP + File I/O)

```java
import java.io.*;

class DateOfBirth {
    private int date;
    private int month;
    private int year;

    public DateOfBirth(int d, int m, int y) {
        date = d;
        month = m;
        year = y;
    }

    public void writeFile() throws Exception {
        FileWriter fw = new FileWriter("dob.txt");
        fw.write(date + " " + month + " " + year);
        fw.close();
    }

    public void readFile() throws Exception {
        BufferedReader br =
            new BufferedReader(new FileReader("dob.txt"));

        String data = br.readLine();
        String arr[] = data.split(" ");

        date = Integer.parseInt(arr[0]);
        month = Integer.parseInt(arr[1]);
        year = Integer.parseInt(arr[2]);

        br.close();
    }

    public void display() {
        System.out.println(
            "Date of Birth: "
            + date + "-" + month + "-" + year);
    }
}

public class Main {
    public static void main(String[] args) throws Exception {

        DateOfBirth person =
            new DateOfBirth(3, 8, 1992);

        person.writeFile();
        person.readFile();
        person.display();
    }
}
```

---

# 5. Python (OOP + File I/O)

```python
class DateOfBirth:

    def __init__(self, date, month, year):
        self.date = date
        self.month = month
        self.year = year

    def write_file(self):
        with open("dob.txt", "w") as f:
            f.write(f"{self.date} {self.month} {self.year}")

    def read_file(self):
        with open("dob.txt", "r") as f:
            data = f.read().split()

            self.date = int(data[0])
            self.month = int(data[1])
            self.year = int(data[2])

    def display(self):
        print(
            f"Date of Birth: "
            f"{self.date}-{self.month}-{self.year}"
        )


person = DateOfBirth(3, 8, 1992)

person.write_file()
person.read_file()
person.display()
```

---

# 6. Python (Dictionary/Structure-like + File I/O)

```python
person = {
    "date": 3,
    "month": 8,
    "year": 1992
}

with open("dob.txt", "w") as f:
    f.write(
        f"{person['date']} "
        f"{person['month']} "
        f"{person['year']}"
    )

with open("dob.txt", "r") as f:
    data = f.read().split()

print(
    f"{data[0]}-{data[1]}-{data[2]}"
)
```

### Output (All Programs)

```text
Date of Birth: 3-8-1992
```

### Concepts Covered

* **C** → Structure + Binary File I/O (`fwrite`, `fread`)
* **C++** → Structure/Class + File Streams (`ofstream`, `ifstream`)
* **Java** → Class + `FileWriter`, `FileReader`, `BufferedReader`
* **Python** → Class/Dictionary + `open()`, `read()`, `write()`
