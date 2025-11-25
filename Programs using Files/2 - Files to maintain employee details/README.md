Below are **clean, corrected, modern versions** of your employee-file program in **C, C++, Java, Python, and Python Tkinter**.

Each program:

✔ Takes Employee ID, Name, Address, Salary
✔ Writes to **Employee.txt**
✔ Calculates DA (50%), Deduction (10%), Net Salary
✔ Writes to **Emp_sal.txt**
✔ Displays all details

---

# ✅ **C Program – Employee File Management**

(Corrected version of your code, no `gets()`, no `flushall()`)

```c
#include <stdio.h>
#include <stdlib.h>

int main() {
    FILE *emp, *empsal;
    int id, sal;
    float da, d, net;
    char na[100], add[100];

    printf("Enter ID: ");
    scanf("%d", &id);
    getchar(); // clear newline

    printf("Enter Name: ");
    fgets(na, sizeof(na), stdin);

    printf("Enter Address: ");
    fgets(add, sizeof(add), stdin);

    printf("Enter Basic Pay: ");
    scanf("%d", &sal);

    emp = fopen("Employee.txt", "w");
    if (emp == NULL) {
        printf("File error!");
        exit(1);
    }

    fprintf(emp, "ID=%d\nName=%sAddress=%sBP=%d\n", id, na, add, sal);
    fclose(emp);

    da = sal * 0.50;
    d = sal * 0.10;
    net = sal + da - d;

    empsal = fopen("Emp_sal.txt", "w");
    fprintf(empsal, "ID=%d\nName=%sAddress=%sBP=%d\nDA=%.2f\nDeduction=%.2f\nNet Salary=%.2f\n",
            id, na, add, sal, da, d, net);
    fclose(empsal);

    printf("\n------ EMPLOYEE DETAILS ------\n");
    printf("ID: %d\n", id);
    printf("Name: %s", na);
    printf("Address: %s", add);
    printf("Basic Pay: %d\nDA: %.2f\nDeduction: %.2f\nNet Salary: %.2f\n", sal, da, d, net);

    return 0;
}
```

---

# ✅ **C++ Program – Employee File Management**

```cpp
#include <iostream>
#include <fstream>
using namespace std;

int main() {
    int id, sal;
    string name, address;
    float da, d, net;

    cout << "Enter ID: ";
    cin >> id;
    cin.ignore();

    cout << "Enter Name: ";
    getline(cin, name);

    cout << "Enter Address: ";
    getline(cin, address);

    cout << "Enter Basic Pay: ";
    cin >> sal;

    ofstream emp("Employee.txt");
    emp << "ID=" << id << "\nName=" << name << "\nAddress=" << address << "\nBP=" << sal;
    emp.close();

    da = sal * 0.50;
    d = sal * 0.10;
    net = sal + da - d;

    ofstream empsal("Emp_sal.txt");
    empsal << "ID=" << id << "\nName=" << name << "\nAddress=" << address
           << "\nBP=" << sal << "\nDA=" << da << "\nDeduction=" << d << "\nNet=" << net;
    empsal.close();

    cout << "\n------ EMPLOYEE DETAILS ------\n";
    cout << "ID: " << id << "\nName: " << name << "\nAddress: " << address
         << "\nBP: " << sal << "\nDA: " << da << "\nDeduction: " << d << "\nNet Salary: " << net << endl;

    return 0;
}
```

---

# ✅ **Java Program – Employee File Management**

```java
import java.io.FileWriter;
import java.util.Scanner;

public class EmployeeFile {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter ID: ");
        int id = sc.nextInt();
        sc.nextLine();

        System.out.print("Enter Name: ");
        String name = sc.nextLine();

        System.out.print("Enter Address: ");
        String address = sc.nextLine();

        System.out.print("Enter Basic Pay: ");
        int salary = sc.nextInt();

        float da = salary * 0.50f;
        float d = salary * 0.10f;
        float net = salary + da - d;

        try {
            FileWriter emp = new FileWriter("Employee.txt");
            emp.write("ID=" + id + "\nName=" + name + "\nAddress=" + address + "\nBP=" + salary);
            emp.close();

            FileWriter empsal = new FileWriter("Emp_sal.txt");
            empsal.write("ID=" + id + "\nName=" + name + "\nAddress=" + address +
                    "\nBP=" + salary + "\nDA=" + da + "\nDeduction=" + d + "\nNet=" + net);
            empsal.close();

        } catch (Exception e) {
            System.out.println("File error!");
        }

        System.out.println("\n------ EMPLOYEE DETAILS ------");
        System.out.println("ID: " + id);
        System.out.println("Name: " + name);
        System.out.println("Address: " + address);
        System.out.println("Basic Pay: " + salary);
        System.out.println("DA: " + da);
        System.out.println("Deduction: " + d);
        System.out.println("Net Salary: " + net);
    }
}
```

---

# ✅ **Python Program – Employee File Management**

```python
id = int(input("Enter ID: "))
name = input("Enter Name: ")
address = input("Enter Address: ")
salary = int(input("Enter Basic Pay: "))

da = salary * 0.50
deduction = salary * 0.10
net = salary + da - deduction

with open("Employee.txt", "w") as f:
    f.write(f"ID={id}\nName={name}\nAddress={address}\nBP={salary}")

with open("Emp_sal.txt", "w") as f:
    f.write(f"ID={id}\nName={name}\nAddress={address}\nBP={salary}\nDA={da}\nDeduction={deduction}\nNet={net}")

print("\n------ EMPLOYEE DETAILS ------")
print("ID:", id)
print("Name:", name)
print("Address:", address)
print("Basic Pay:", salary)
print("DA:", da)
print("Deduction:", deduction)
print("Net Salary:", net)
```

---

# ✅ **Tkinter GUI – Employee File Management**

```python
import tkinter as tk
from tkinter import messagebox

def save_data():
    emp_id = id_entry.get()
    name = name_entry.get()
    address = address_entry.get()
    salary = float(salary_entry.get())

    da = salary * 0.50
    deduction = salary * 0.10
    net = salary + da - deduction

    with open("Employee.txt", "w") as f:
        f.write(f"ID={emp_id}\nName={name}\nAddress={address}\nBP={salary}")

    with open("Emp_sal.txt", "w") as f:
        f.write(f"ID={emp_id}\nName={name}\nAddress={address}\nBP={salary}\nDA={da}\nDeduction={deduction}\nNet={net}")

    messagebox.showinfo("Success", "Employee details saved successfully!")

root = tk.Tk()
root.title("Employee Details")

tk.Label(root, text="ID").pack()
id_entry = tk.Entry(root)
id_entry.pack()

tk.Label(root, text="Name").pack()
name_entry = tk.Entry(root)
name_entry.pack()

tk.Label(root, text="Address").pack()
address_entry = tk.Entry(root)
address_entry.pack()

tk.Label(root, text="Basic Pay").pack()
salary_entry = tk.Entry(root)
salary_entry.pack()

tk.Button(root, text="Save to File", command=save_data).pack(pady=10)

root.mainloop()
```

---

If you want, I can also provide:

✅ Tkinter with multi-line TextBox
✅ Save multiple employees
✅ Display saved employee records
✅ C/C++ file append mode version

Just tell me!
