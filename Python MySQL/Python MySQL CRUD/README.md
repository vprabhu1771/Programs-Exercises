If you want to build a **Python MySQL CRUD (Create, Read, Update, Delete)** application, here's a simple example using the **`mysql-connector-python`** package.

## 1. Install MySQL Connector

```bash
pip install mysql-connector-python
```

---

## 2. Create MySQL Database

```sql
CREATE DATABASE company;

USE company;

CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    email VARCHAR(100),
    salary DECIMAL(10,2)
);
```

---

## 3. Database Connection (`database.py`)

```python
import mysql.connector

def get_connection():
    return mysql.connector.connect(
        host="localhost",
        user="root",
        password="your_password",
        database="company"
    )
```

---

# CREATE

```python
from database import get_connection

def create_employee(name, email, salary):
    conn = get_connection()
    cursor = conn.cursor()

    sql = """
    INSERT INTO employees(name, email, salary)
    VALUES(%s, %s, %s)
    """

    cursor.execute(sql, (name, email, salary))

    conn.commit()

    print("Employee Added")

    cursor.close()
    conn.close()


create_employee("John", "john@gmail.com", 50000)
```

---

# READ

```python
from database import get_connection

def get_employees():
    conn = get_connection()
    cursor = conn.cursor()

    cursor.execute("SELECT * FROM employees")

    rows = cursor.fetchall()

    for row in rows:
        print(row)

    cursor.close()
    conn.close()

get_employees()
```

Output

```
(1, 'John', 'john@gmail.com', Decimal('50000.00'))
```

---

# READ Single Record

```python
from database import get_connection

def get_employee(emp_id):
    conn = get_connection()
    cursor = conn.cursor()

    cursor.execute(
        "SELECT * FROM employees WHERE id=%s",
        (emp_id,)
    )

    employee = cursor.fetchone()

    print(employee)

    cursor.close()
    conn.close()

get_employee(1)
```

---

# UPDATE

```python
from database import get_connection

def update_employee(emp_id, name, email, salary):
    conn = get_connection()
    cursor = conn.cursor()

    sql = """
    UPDATE employees
    SET name=%s,
        email=%s,
        salary=%s
    WHERE id=%s
    """

    cursor.execute(sql, (name, email, salary, emp_id))

    conn.commit()

    print("Updated Successfully")

    cursor.close()
    conn.close()

update_employee(1, "Peter", "peter@gmail.com", 70000)
```

---

# DELETE

```python
from database import get_connection

def delete_employee(emp_id):
    conn = get_connection()
    cursor = conn.cursor()

    cursor.execute(
        "DELETE FROM employees WHERE id=%s",
        (emp_id,)
    )

    conn.commit()

    print("Deleted Successfully")

    cursor.close()
    conn.close()

delete_employee(1)
```

---

# Menu Driven CRUD

```python
from database import get_connection

def add():
    name = input("Name : ")
    email = input("Email : ")
    salary = float(input("Salary : "))

    conn = get_connection()
    cursor = conn.cursor()

    cursor.execute(
        "INSERT INTO employees(name,email,salary) VALUES(%s,%s,%s)",
        (name, email, salary)
    )

    conn.commit()
    cursor.close()
    conn.close()

    print("Employee Added")


def view():
    conn = get_connection()
    cursor = conn.cursor()

    cursor.execute("SELECT * FROM employees")

    for row in cursor.fetchall():
        print(row)

    cursor.close()
    conn.close()


def update():
    id = int(input("Employee ID: "))
    name = input("New Name: ")
    email = input("New Email: ")
    salary = float(input("New Salary: "))

    conn = get_connection()
    cursor = conn.cursor()

    cursor.execute("""
        UPDATE employees
        SET name=%s,email=%s,salary=%s
        WHERE id=%s
    """, (name, email, salary, id))

    conn.commit()

    cursor.close()
    conn.close()

    print("Updated")


def delete():
    id = int(input("Employee ID: "))

    conn = get_connection()
    cursor = conn.cursor()

    cursor.execute(
        "DELETE FROM employees WHERE id=%s",
        (id,)
    )

    conn.commit()

    cursor.close()
    conn.close()

    print("Deleted")


while True:

    print("""
1.Add Employee
2.View Employees
3.Update Employee
4.Delete Employee
5.Exit
""")

    choice = input("Enter Choice: ")

    if choice == "1":
        add()

    elif choice == "2":
        view()

    elif choice == "3":
        update()

    elif choice == "4":
        delete()

    elif choice == "5":
        break

    else:
        print("Invalid Choice")
```

## Recommended Project Structure

```
python_mysql_crud/
│
├── database.py          # Database connection
├── crud.py              # CRUD functions
├── main.py              # Menu or application entry point
├── requirements.txt
└── README.md
```

This structure is suitable for small applications. For larger projects, you can further organize the code into packages (e.g., `models`, `services`, and `controllers`) or use a web framework such as Flask, FastAPI, or Django.
