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
    print("Employees View Successfully")

def update():
    id = int(input("Employee ID : "))
    name = input("New Name : ")
    email = input("New Email : ")
    salary = float(input("New Salary : "))

    conn = get_connection()
    cursor = conn.cursor()

    cursor.execute("""
        UPDATE employees
        SET name = %s,email = %s,salary = %s
        WHERE id = %s
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

def display(rows):
    if rows:
        print("\nID\tName\tEmail\t\t\tSalary")
        print("-" * 60)
        for row in rows:
            print(f"{row[0]}\t{row[1]}\t{row[2]}\t{row[3]}")
    else:
        print("No records found.")


def search_in():
    ids = input("Enter Employee IDs (comma separated): ")

    conn = get_connection()
    cursor = conn.cursor()

    id_list = [int(x.strip()) for x in ids.split(",")]

    placeholders = ",".join(["%s"] * len(id_list))

    sql = f"""
    SELECT *
    FROM employees
    WHERE id IN ({placeholders})
    """

    cursor.execute(sql, id_list)

    display(cursor.fetchall())


def search_not_in():
    ids = input("Enter Employee IDs (comma separated): ")

    conn = get_connection()
    cursor = conn.cursor()

    id_list = [int(x.strip()) for x in ids.split(",")]

    placeholders = ",".join(["%s"] * len(id_list))

    sql = f"""
    SELECT *
    FROM employees
    WHERE id NOT IN ({placeholders})
    """

    cursor.execute(sql, id_list)

    display(cursor.fetchall())


def search_between():
    start = float(input("Enter Minimum Salary: "))
    end = float(input("Enter Maximum Salary: "))

    conn = get_connection()
    cursor = conn.cursor()

    sql = """
    SELECT *
    FROM employees
    WHERE salary BETWEEN %s AND %s
    """

    cursor.execute(sql, (start, end))

    display(cursor.fetchall())


def search_not_between():
    start = float(input("Enter Minimum Salary: "))
    end = float(input("Enter Maximum Salary: "))

    conn = get_connection()
    cursor = conn.cursor()

    sql = """
    SELECT *
    FROM employees
    WHERE salary NOT BETWEEN %s AND %s
    """

    cursor.execute(sql, (start, end))

    display(cursor.fetchall())

while True:
    print("""
    1. Add Employees
    2. View Employees
    3. Update Employees
    4. Delete Employees
    5. Search Employee (IN)
    6. Search Employee (NOT IN)
    7. Search Salary (BETWEEN)
    8. Search Salary (NOT BETWEEN)
    9. Exit
    
    """)
    choice = input("Enter your choice: ")
    if choice == "1":
        add()
    elif choice == "2":
        view()
    elif choice == "3":
        update()
    elif choice == "4":
        delete()
    elif choice == "5":
        search_in()
    elif choice == "6":
        search_not_in()
    elif choice == "7":
        search_between()
    elif choice == "8":
        search_not_between()
    elif choice == "9":
        print("Thank You!")
        break
    else:
        print("Invalid Choice")
```
