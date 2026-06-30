Below is the complete Java JDBC equivalent of your Python program. It includes:

* ✅ Add Employee
* ✅ View Employees
* ✅ Update Employee
* ✅ Delete Employee
* ✅ Search Employee (IN)
* ✅ Search Employee (NOT IN)
* ✅ Search Salary (BETWEEN)
* ✅ Search Salary (NOT BETWEEN)
* ✅ Menu-Driven Program

---

## DatabaseConnection.java

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;

public class DatabaseConnection {

    private static final String URL = "jdbc:mysql://localhost:3306/company";
    private static final String USER = "root";
    private static final String PASSWORD = "your_password";

    public static Connection getConnection() throws SQLException {
        return DriverManager.getConnection(URL, USER, PASSWORD);
    }
}
```

---

## EmployeeCRUD.java

```java
import java.sql.*;
import java.util.Scanner;

public class EmployeeCRUD {

    static Scanner sc = new Scanner(System.in);

    // Add Employee
    static void add() {

        System.out.print("Name : ");
        String name = sc.nextLine();

        System.out.print("Email : ");
        String email = sc.nextLine();

        System.out.print("Salary : ");
        double salary = sc.nextDouble();
        sc.nextLine();

        String sql = "INSERT INTO employees(name,email,salary) VALUES(?,?,?)";

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

    // View Employees
    static void view() {

        String sql = "SELECT * FROM employees";

        try (Connection conn = DatabaseConnection.getConnection();
             PreparedStatement ps = conn.prepareStatement(sql);
             ResultSet rs = ps.executeQuery()) {

            display(rs);

            System.out.println("Employees View Successfully");

        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    // Update Employee
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
                "UPDATE employees SET name=?, email=?, salary=? WHERE id=?";

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

    // Delete Employee
    static void delete() {

        System.out.print("Employee ID : ");
        int id = sc.nextInt();
        sc.nextLine();

        String sql = "DELETE FROM employees WHERE id=?";

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

    // Display Result
    static void display(ResultSet rs) throws SQLException {

        boolean found = false;

        System.out.println();
        System.out.printf("%-5s %-15s %-30s %-10s%n",
                "ID", "Name", "Email", "Salary");
        System.out.println("--------------------------------------------------------------");

        while (rs.next()) {

            found = true;

            System.out.printf("%-5d %-15s %-30s %-10.2f%n",
                    rs.getInt("id"),
                    rs.getString("name"),
                    rs.getString("email"),
                    rs.getDouble("salary"));
        }

        if (!found)
            System.out.println("No Records Found.");
    }

    // Search IN
    static void searchIn() {

        System.out.print("Enter Employee IDs (comma separated): ");
        String input = sc.nextLine();

        String[] ids = input.split(",");

        StringBuilder placeholders = new StringBuilder();

        for (int i = 0; i < ids.length; i++) {
            placeholders.append("?");

            if (i < ids.length - 1)
                placeholders.append(",");
        }

        String sql =
                "SELECT * FROM employees WHERE id IN (" +
                        placeholders + ")";

        try (Connection conn = DatabaseConnection.getConnection();
             PreparedStatement ps = conn.prepareStatement(sql)) {

            for (int i = 0; i < ids.length; i++)
                ps.setInt(i + 1, Integer.parseInt(ids[i].trim()));

            ResultSet rs = ps.executeQuery();

            display(rs);

        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    // Search NOT IN
    static void searchNotIn() {

        System.out.print("Enter Employee IDs (comma separated): ");
        String input = sc.nextLine();

        String[] ids = input.split(",");

        StringBuilder placeholders = new StringBuilder();

        for (int i = 0; i < ids.length; i++) {
            placeholders.append("?");

            if (i < ids.length - 1)
                placeholders.append(",");
        }

        String sql =
                "SELECT * FROM employees WHERE id NOT IN (" +
                        placeholders + ")";

        try (Connection conn = DatabaseConnection.getConnection();
             PreparedStatement ps = conn.prepareStatement(sql)) {

            for (int i = 0; i < ids.length; i++)
                ps.setInt(i + 1, Integer.parseInt(ids[i].trim()));

            ResultSet rs = ps.executeQuery();

            display(rs);

        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    // Search BETWEEN
    static void searchBetween() {

        System.out.print("Minimum Salary : ");
        double min = sc.nextDouble();

        System.out.print("Maximum Salary : ");
        double max = sc.nextDouble();

        sc.nextLine();

        String sql =
                "SELECT * FROM employees WHERE salary BETWEEN ? AND ?";

        try (Connection conn = DatabaseConnection.getConnection();
             PreparedStatement ps = conn.prepareStatement(sql)) {

            ps.setDouble(1, min);
            ps.setDouble(2, max);

            ResultSet rs = ps.executeQuery();

            display(rs);

        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    // Search NOT BETWEEN
    static void searchNotBetween() {

        System.out.print("Minimum Salary : ");
        double min = sc.nextDouble();

        System.out.print("Maximum Salary : ");
        double max = sc.nextDouble();

        sc.nextLine();

        String sql =
                "SELECT * FROM employees WHERE salary NOT BETWEEN ? AND ?";

        try (Connection conn = DatabaseConnection.getConnection();
             PreparedStatement ps = conn.prepareStatement(sql)) {

            ps.setDouble(1, min);
            ps.setDouble(2, max);

            ResultSet rs = ps.executeQuery();

            display(rs);

        } catch (Exception e) {
            e.printStackTrace();
        }
    }

    // Main Menu
    public static void main(String[] args) {

        while (true) {

            System.out.println("\n===== EMPLOYEE MANAGEMENT =====");
            System.out.println("1. Add Employee");
            System.out.println("2. View Employees");
            System.out.println("3. Update Employee");
            System.out.println("4. Delete Employee");
            System.out.println("5. Search Employee (IN)");
            System.out.println("6. Search Employee (NOT IN)");
            System.out.println("7. Search Salary (BETWEEN)");
            System.out.println("8. Search Salary (NOT BETWEEN)");
            System.out.println("9. Exit");

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
                    searchIn();
                    break;

                case 6:
                    searchNotIn();
                    break;

                case 7:
                    searchBetween();
                    break;

                case 8:
                    searchNotBetween();
                    break;

                case 9:
                    System.out.println("Thank You!");
                    System.exit(0);

                default:
                    System.out.println("Invalid Choice");
            }
        }
    }
}
```

### Project Structure

```
JavaJDBCCrud/
│
├── DatabaseConnection.java
└── EmployeeCRUD.java
```

This Java program is a one-to-one conversion of your Python MySQL CRUD application using JDBC, including the dynamic `IN`/`NOT IN` queries, `BETWEEN`/`NOT BETWEEN` salary searches, and the same menu-driven workflow.
