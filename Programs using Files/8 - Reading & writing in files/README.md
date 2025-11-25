Here are the **C, C++, Java, Python, and Tkinter** versions of your program for **reading & writing a structure/object to a file**.

---

# ✅ **1. C Program – Read & Write Structure in File**

```c
#include <stdio.h>

struct stud {
    int roll;
    char name[12];
    int percent;
};

int main() {
    FILE *fp;
    struct stud s = {10, "SMJC", 80};
    struct stud s1;

    fp = fopen("ip.txt", "wb");
    fwrite(&s, sizeof(s), 1, fp);
    fclose(fp);

    fp = fopen("ip.txt", "rb");
    fread(&s1, sizeof(s1), 1, fp);
    fclose(fp);

    printf("\nRoll : %d", s1.roll);
    printf("\nName : %s", s1.name);
    printf("\nPercent : %d", s1.percent);

    return 0;
}
```

---

# ✅ **2. C++ Program – Read & Write Object to File**

```cpp
#include <iostream>
#include <fstream>
using namespace std;

struct stud {
    int roll;
    char name[12];
    int percent;
};

int main() {
    stud s = {10, "SMJC", 80};
    stud s1;

    ofstream fout("ip.txt", ios::binary);
    fout.write((char*)&s, sizeof(s));
    fout.close();

    ifstream fin("ip.txt", ios::binary);
    fin.read((char*)&s1, sizeof(s1));
    fin.close();

    cout << "\nRoll : " << s1.roll;
    cout << "\nName : " << s1.name;
    cout << "\nPercent : " << s1.percent;

    return 0;
}
```

---

# ✅ **3. Java Program – Read & Write Object to File**

(Java uses serialization)

```java
import java.io.*;

class Student implements Serializable {
    int roll;
    String name;
    int percent;

    Student(int r, String n, int p) {
        roll = r;
        name = n;
        percent = p;
    }
}

public class Main {
    public static void main(String[] args) {
        try {
            Student s = new Student(10, "SMJC", 80);

            ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("ip.dat"));
            out.writeObject(s);
            out.close();

            ObjectInputStream in = new ObjectInputStream(new FileInputStream("ip.dat"));
            Student s1 = (Student) in.readObject();
            in.close();

            System.out.println("Roll : " + s1.roll);
            System.out.println("Name : " + s1.name);
            System.out.println("Percent : " + s1.percent);

        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

---

# ✅ **4. Python Program – Read & Write Object Using pickle**

```python
import pickle

class Student:
    def __init__(self, roll, name, percent):
        self.roll = roll
        self.name = name
        self.percent = percent

s = Student(10, "SMJC", 80)

# Write
with open("ip.pkl", "wb") as f:
    pickle.dump(s, f)

# Read
with open("ip.pkl", "rb") as f:
    s1 = pickle.load(f)

print("Roll :", s1.roll)
print("Name :", s1.name)
print("Percent :", s1.percent)
```

---

# ✅ **5. Tkinter GUI Version – Read & Write Object**

```python
import tkinter as tk
import pickle
from tkinter import messagebox

class Student:
    def __init__(self, roll, name, percent):
        self.roll = roll
        self.name = name
        self.percent = percent

def write_data():
    s = Student(10, "SMJC", 80)
    with open("ip.pkl", "wb") as f:
        pickle.dump(s, f)
    messagebox.showinfo("Success", "Data Written to File")

def read_data():
    try:
        with open("ip.pkl", "rb") as f:
            s = pickle.load(f)
        output.delete("1.0", tk.END)
        output.insert(tk.END, f"Roll: {s.roll}\nName: {s.name}\nPercent: {s.percent}")
    except:
        messagebox.showerror("Error", "File Not Found")

root = tk.Tk()
root.title("Read & Write Student File")

tk.Button(root, text="Write Data", command=write_data).pack(pady=5)
tk.Button(root, text="Read Data", command=read_data).pack(pady=5)

output = tk.Text(root, width=40, height=5)
output.pack()

root.mainloop()
```

---

If you need:

✅ GUI in **Qt (C++)**
✅ GUI in **Java Swing / JavaFX**
✅ Save multiple student records
✅ Use CSV instead of binary

Just tell me!
