Below are **clean, corrected, working versions** of your **Employee Structure File Processing Program** in **C, C++, Java, Python, and Tkinter**.

All versions:

✔ Use employee structure/class
✔ Write multiple employee records to a file
✔ Read back from the file
✔ Print employees where **salary < 4500** AND **age > 35**

---

# ✅ **C Program (Corrected Version)**

```c
#include <stdio.h>
#include <stdlib.h>

struct employee {
    int empid;
    char name[25];
    int age;
    long int sal;
};

int main() {
    struct employee e[30], emp[30];
    FILE *fp;
    int i, n;

    printf("Enter number of employees: ");
    scanf("%d", &n);

    fp = fopen("efile.dat", "wb");
    if (!fp) {
        printf("File error!");
        exit(1);
    }

    for (i = 0; i < n; i++) {
        printf("Enter empid, name, age, salary:\n");
        scanf("%d %s %d %ld", &e[i].empid, e[i].name, &e[i].age, &e[i].sal);
    }

    fwrite(e, sizeof(struct employee), n, fp);
    fclose(fp);

    fp = fopen("efile.dat", "rb");
    fread(emp, sizeof(struct employee), n, fp);

    printf("\nEmployees with sal < 4500 AND age > 35:\n");

    for (i = 0; i < n; i++) {
        if (emp[i].sal < 4500 && emp[i].age > 35) {
            printf("\nEmployee ID: %d\nName: %s\nAge: %d\nSalary: %ld\n",
                   emp[i].empid, emp[i].name, emp[i].age, emp[i].sal);
        }
    }

    fclose(fp);
    return 0;
}
```

---

# ✅ **C++ Program**

```cpp
#include <iostream>
#include <fstream>
using namespace std;

struct Employee {
    int empid;
    char name[25];
    int age;
    long sal;
};

int main() {
    Employee e[30], emp[30];
    int n;

    cout << "Enter number of employees: ";
    cin >> n;

    ofstream fout("efile.dat", ios::binary);
    for (int i = 0; i < n; i++) {
        cout << "Enter empid, name, age, salary:\n";
        cin >> e[i].empid >> e[i].name >> e[i].age >> e[i].sal;
    }

    fout.write((char*)e, sizeof(Employee) * n);
    fout.close();

    ifstream fin("efile.dat", ios::binary);
    fin.read((char*)emp, sizeof(Employee) * n);
    fin.close();

    cout << "\nEmployees with sal < 4500 AND age > 35:\n";
    for (int i = 0; i < n; i++) {
        if (emp[i].sal < 4500 && emp[i].age > 35) {
            cout << "\nEmployee ID: " << emp[i].empid
                 << "\nName: " << emp[i].name
                 << "\nAge: " << emp[i].age
                 << "\nSalary: " << emp[i].sal << endl;
        }
    }

    return 0;
}
```

---

# ✅ **Java Program**

Java doesn’t support binary struct I/O like C, so we use Serializable.

```java
import java.io.*;
import java.util.Scanner;

class Employee implements Serializable {
    int empid;
    String name;
    int age;
    long sal;
}

public class EmployeeFile {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        try {
            System.out.print("Enter number of employees: ");
            int n = sc.nextInt();

            Employee[] e = new Employee[n];
            ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("efile.dat"));

            for (int i = 0; i < n; i++) {
                e[i] = new Employee();
                System.out.println("Enter empid, name, age, salary:");
                e[i].empid = sc.nextInt();
                e[i].name = sc.next();
                e[i].age = sc.nextInt();
                e[i].sal = sc.nextLong();
            }

            out.writeObject(e);
            out.close();

            ObjectInputStream in = new ObjectInputStream(new FileInputStream("efile.dat"));
            Employee[] emp = (Employee[]) in.readObject();
            in.close();

            System.out.println("\nEmployees with sal < 4500 AND age > 35:");
            for (Employee x : emp) {
                if (x.sal < 4500 && x.age > 35) {
                    System.out.println("\nID: " + x.empid +
                            "\nName: " + x.name +
                            "\nAge: " + x.age +
                            "\nSalary: " + x.sal);
                }
            }

        } catch (Exception ex) {
            ex.printStackTrace();
        }

        sc.close();
    }
}
```

---

# ✅ **Python Program**

Python does not have struct binary support like C, so we use Pickle.

```python
import pickle

class Employee:
    def __init__(self, empid, name, age, sal):
        self.empid = empid
        self.name = name
        self.age = age
        self.sal = sal

n = int(input("Enter number of employees: "))

employees = []
for i in range(n):
    empid = int(input("Enter EmpID: "))
    name = input("Enter Name: ")
    age = int(input("Enter Age: "))
    sal = int(input("Enter Salary: "))
    employees.append(Employee(empid, name, age, sal))

# Write to file
with open("efile.dat", "wb") as f:
    pickle.dump(employees, f)

# Read back
with open("efile.dat", "rb") as f:
    emp = pickle.load(f)

print("\nEmployees with sal < 4500 AND age > 35:")
for e in emp:
    if e.sal < 4500 and e.age > 35:
        print(f"\nID: {e.empid}\nName: {e.name}\nAge: {e.age}\nSalary: {e.sal}")
```

---

# ✅ **Tkinter GUI Version**

This version saves employee records to a binary file using pickle.

```python
import tkinter as tk
from tkinter import messagebox
import pickle

employees = []

def save_employee():
    empid = int(id_entry.get())
    name = name_entry.get()
    age = int(age_entry.get())
    sal = int(sal_entry.get())

    employees.append({"id": empid, "name": name, "age": age, "sal": sal})

    with open("efile.dat", "wb") as f:
        pickle.dump(employees, f)

    messagebox.showinfo("Saved", "Employee added!")
    id_entry.delete(0, tk.END)
    name_entry.delete(0, tk.END)
    age_entry.delete(0, tk.END)
    sal_entry.delete(0, tk.END)

def show_filtered():
    try:
        with open("efile.dat", "rb") as f:
            emp = pickle.load(f)
    except:
        messagebox.showerror("Error", "No employee file found!")
        return

    result = ""
    for e in emp:
        if e["sal"] < 4500 and e["age"] > 35:
            result += f"ID: {e['id']}\nName: {e['name']}\nAge: {e['age']}\nSalary: {e['sal']}\n\n"

    messagebox.showinfo("Filtered Employees", result if result else "No matching employees!")

root = tk.Tk()
root.title("Employee Entry")

tk.Label(root, text="Employee ID").pack()
id_entry = tk.Entry(root)
id_entry.pack()

tk.Label(root, text="Name").pack()
name_entry = tk.Entry(root)
name_entry.pack()

tk.Label(root, text="Age").pack()
age_entry = tk.Entry(root)
age_entry.pack()

tk.Label(root, text="Salary").pack()
sal_entry = tk.Entry(root)
sal_entry.pack()

tk.Button(root, text="Add Employee", command=save_employee).pack(pady=10)
tk.Button(root, text="Show Filtered Employees", command=show_filtered).pack(pady=10)

root.mainloop()
```

---

If you want, I can also give:

✔ Tkinter table view
✔ Append mode (not overwrite)
✔ JSON or CSV version instead of binary
✔ Search employee by ID

Just tell me!
