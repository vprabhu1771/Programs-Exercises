Below is the equivalent **Java JDBC CRUD** application for the same **employees** table.

---

# 1. MySQL Database

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

# 2. Add MySQL JDBC Driver

If using **Maven**

```xml
<dependency>
    <groupId>com.mysql</groupId>
    <artifactId>mysql-connector-j</artifactId>
    <version>9.3.0</version>
</dependency>
```

Or add **mysql-connector-j.jar** to your project.

---

# 3. Database Connection (DatabaseConnection.java)

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

public class DatabaseConnection {

    private static final String URL =
            "jdbc:mysql://localhost:3306/company";

    private static final String USER = "root";
    private static final String PASSWORD = "your_password";

    public static Connection getConnection() throws SQLException {
        return DriverManager.getConnection(URL, USER, PASSWORD);
    }
}
```

---

# CREATE

```java
import java.sql.Connection;
import java.sql.PreparedStatement;

public class CreateEmployee {

    public static void createEmployee(String name,
                                      String email,
                                      double salary) {

        String sql =
                "INSERT INTO employees(name,email,salary) VALUES(?,?,?)";

        try (Connection conn = DatabaseConnection.getConnection();
             PreparedStatement ps = conn.prepareStatement(sql)) {

            ps.setString(1, name);
            ps.setString(2, email);
            ps.setDouble(3, salary);

            ps.executeUpdate();

            System.out.println("Employee Added");

        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    public static void main(String[] args) {

        createEmployee(
                "John",
                "john@gmail.com",
                50000
        );

    }
}
```

---

# READ All Records

```java
import java.sql.*;

public class ReadEmployees {

    public static void getEmployees() {

        String sql = "SELECT * FROM employees";

        try (Connection conn = DatabaseConnection.getConnection();
             PreparedStatement ps = conn.prepareStatement(sql);
             ResultSet rs = ps.executeQuery()) {

            while (rs.next()) {

                System.out.println(
                        rs.getInt("id") + " "
                        + rs.getString("name") + " "
                        + rs.getString("email") + " "
                        + rs.getDouble("salary")
                );

            }

        } catch (Exception e) {
            e.printStackTrace();
        }

    }

    public static void main(String[] args) {

        getEmployees();

    }
}
```

---

# READ Single Record

```java
import java.sql.*;

public class ReadEmployee {

    public static void getEmployee(int id) {

        String sql =
                "SELECT * FROM employees WHERE id=?";

        try (Connection conn = DatabaseConnection.getConnection();
             PreparedStatement ps = conn.prepareStatement(sql)) {

            ps.setInt(1, id);

            ResultSet rs = ps.executeQuery();

            if (rs.next()) {

                System.out.println(
                        rs.getInt("id") + " "
                        + rs.getString("name") + " "
                        + rs.getString("email") + " "
                        + rs.getDouble("salary")
                );

            } else {

                System.out.println("Employee Not Found");

            }

        } catch (Exception e) {
            e.printStackTrace();
        }

    }

    public static void main(String[] args) {

        getEmployee(1);

    }
}
```

---

# UPDATE

```java
import java.sql.*;

public class UpdateEmployee {

    public static void updateEmployee(int id,
                                      String name,
                                      String email,
                                      double salary) {

        String sql =
                "UPDATE employees SET name=?,email=?,salary=? WHERE id=?";

        try (Connection conn = DatabaseConnection.getConnection();
             PreparedStatement ps = conn.prepareStatement(sql)) {

            ps.setString(1, name);
            ps.setString(2, email);
            ps.setDouble(3, salary);
            ps.setInt(4, id);

            int rows = ps.executeUpdate();

            if (rows > 0)
                System.out.println("Updated Successfully");
            else
                System.out.println("Employee Not Found");

        } catch (Exception e) {
            e.printStackTrace();
        }

    }

    public static void main(String[] args) {

        updateEmployee(
                1,
                "Peter",
                "peter@gmail.com",
                70000
        );

    }
}
```

---

# DELETE

```java
import java.sql.*;

public class DeleteEmployee {

    public static void deleteEmployee(int id) {

        String sql =
                "DELETE FROM employees WHERE id=?";

        try (Connection conn = DatabaseConnection.getConnection();
             PreparedStatement ps = conn.prepareStatement(sql)) {

            ps.setInt(1, id);

            int rows = ps.executeUpdate();

            if (rows > 0)
                System.out.println("Deleted Successfully");
            else
                System.out.println("Employee Not Found");

        } catch (Exception e) {
            e.printStackTrace();
        }

    }

    public static void main(String[] args) {

        deleteEmployee(1);

    }
}
```

---

# Menu Driven CRUD (Main.java)

```java
import java.sql.*;
import java.util.Scanner;

public class Main {

    static Scanner sc = new Scanner(System.in);

    static void add() {

        System.out.print("Name : ");
        String name = sc.nextLine();

        System.out.print("Email : ");
        String email = sc.nextLine();

        System.out.print("Salary : ");
        double salary = sc.nextDouble();
        sc.nextLine();

        String sql =
                "INSERT INTO employees(name,email,salary) VALUES(?,?,?)";

        try (Connection conn = DatabaseConnection.getConnection();
             PreparedStatement ps = conn.prepareStatement(sql)) {

            ps.setString(1, name);
            ps.setString(2, email);
            ps.setDouble(3, salary);

            ps.executeUpdate();

            System.out.println("Employee Added");

        } catch (Exception e) {
            e.printStackTrace();
        }

    }

    static void view() {

        String sql = "SELECT * FROM employees";

        try (Connection conn = DatabaseConnection.getConnection();
             PreparedStatement ps = conn.prepareStatement(sql);
             ResultSet rs = ps.executeQuery()) {

            while (rs.next()) {

                System.out.printf("%d %s %s %.2f%n",
                        rs.getInt("id"),
                        rs.getString("name"),
                        rs.getString("email"),
                        rs.getDouble("salary"));

            }

        } catch (Exception e) {
            e.printStackTrace();
        }

    }

    static void update() {

        System.out.print("Employee ID : ");
        int id = sc.nextInt();
        sc.nextLine();

        System.out.print("New Name : ");
        String name = sc.nextLine();

        System.out.print("New Email : ");
        String email = sc.nextLine();

        System.out.print("New Salary : ");
        double salary = sc.nextDouble();
        sc.nextLine();

        String sql =
                "UPDATE employees SET name=?,email=?,salary=? WHERE id=?";

        try (Connection conn = DatabaseConnection.getConnection();
             PreparedStatement ps = conn.prepareStatement(sql)) {

            ps.setString(1, name);
            ps.setString(2, email);
            ps.setDouble(3, salary);
            ps.setInt(4, id);

            if (ps.executeUpdate() > 0)
                System.out.println("Updated");
            else
                System.out.println("Employee Not Found");

        } catch (Exception e) {
            e.printStackTrace();
        }

    }

    static void delete() {

        System.out.print("Employee ID : ");
        int id = sc.nextInt();
        sc.nextLine();

        String sql =
                "DELETE FROM employees WHERE id=?";

        try (Connection conn = DatabaseConnection.getConnection();
             PreparedStatement ps = conn.prepareStatement(sql)) {

            ps.setInt(1, id);

            if (ps.executeUpdate() > 0)
                System.out.println("Deleted");
            else
                System.out.println("Employee Not Found");

        } catch (Exception e) {
            e.printStackTrace();
        }

    }

    public static void main(String[] args) {

        while (true) {

            System.out.println("\n===== MENU =====");
            System.out.println("1. Add Employee");
            System.out.println("2. View Employees");
            System.out.println("3. Update Employee");
            System.out.println("4. Delete Employee");
            System.out.println("5. Exit");

            System.out.print("Enter Choice : ");
            int choice = sc.nextInt();
            sc.nextLine();

            switch (choice) {

                case 1:
                    add();
                    break;

                case 2:
                    view();
                    break;

                case 3:
                    update();
                    break;

                case 4:
                    delete();
                    break;

                case 5:
                    System.exit(0);

                default:
                    System.out.println("Invalid Choice");
            }

        }

    }
}
```

---

# Recommended Project Structure

```text
JavaJDBCCrud/
│
├── src/
│   ├── DatabaseConnection.java
│   ├── CreateEmployee.java
│   ├── ReadEmployees.java
│   ├── ReadEmployee.java
│   ├── UpdateEmployee.java
│   ├── DeleteEmployee.java
│   └── Main.java
│
├── lib/
│   └── mysql-connector-j.jar
│
└── README.md
```

This structure works well for learning JDBC. For larger applications, a layered architecture is recommended:

```text
EmployeeManagement/
│
├── model/
│   └── Employee.java
├── dao/
│   ├── EmployeeDAO.java
│   └── EmployeeDAOImpl.java
├── util/
│   └── DatabaseConnection.java
├── service/
│   └── EmployeeService.java
└── Main.java
```

This DAO-based approach separates database access from business logic, making the application easier to maintain and extend.
