Below is a **complete OOP example** in Java including:

✔ **Class**
✔ **Constructor**
✔ **Getters/Setters**
✔ **toString()**
✔ **Inheritance**
✔ **Polymorphism (method overriding)**
✔ **Encapsulation**

---

# ✅ **User.java (Base Class – Encapsulation + Constructor + toString)**

```java
public class User {
    private String name;
    private int age;
    private String mobile;
    private String address;

    // Constructor
    public User(String name, int age, String mobile, String address) {
        this.name = name;
        this.age = age;
        this.mobile = mobile;
        this.address = address;
    }

    // Getters
    public String getName() { return name; }
    public int getAge() { return age; }
    public String getMobile() { return mobile; }
    public String getAddress() { return address; }

    // Setters
    public void setName(String name) { this.name = name; }
    public void setAge(int age) { this.age = age; }
    public void setMobile(String mobile) { this.mobile = mobile; }
    public void setAddress(String address) { this.address = address; }

    // toString()
    @Override
    public String toString() {
        return "User Details:\n" +
               "Name: " + name + "\n" +
               "Age: " + age + "\n" +
               "Mobile: " + mobile + "\n" +
               "Address: " + address;
    }

    // Polymorphism: method to be overridden
    public String role() {
        return "I am a general user.";
    }
}
```

---

# ✅ **Employee.java (Inheritance + Method Overriding – Polymorphism)**

```java
public class Employee extends User {

    private double salary;

    // Constructor using super()
    public Employee(String name, int age, String mobile, String address, double salary) {
        super(name, age, mobile, address);
        this.salary = salary;
    }

    public double getSalary() { return salary; }
    public void setSalary(double salary) { this.salary = salary; }

    // Method overriding (Polymorphism)
    @Override
    public String role() {
        return "I am an Employee and I earn $" + salary;
    }

    @Override
    public String toString() {
        return super.toString() + "\nSalary: " + salary;
    }
}
```

---

# ✅ **Student.java (Inheritance another example + Overriding)**

```java
public class Student extends User {

    private String course;

    public Student(String name, int age, String mobile, String address, String course) {
        super(name, age, mobile, address);
        this.course = course;
    }

    // Overriding method
    @Override
    public String role() {
        return "I am a Student studying " + course;
    }

    @Override
    public String toString() {
        return super.toString() + "\nCourse: " + course;
    }
}
```

---

# ✅ **App.java (Main Program – Polymorphism Example)**

```java
public class App {

    public static void main(String[] args) {

        // Using constructor
        User user = new User("John Doe", 30, "1234567890", "New York");
        Employee emp = new Employee("Alice", 28, "9876543210", "California", 55000);
        Student stu = new Student("Bob", 20, "9998887777", "Texas", "Computer Science");

        // Polymorphism in action
        User ref1 = emp;   // Employee → User reference
        User ref2 = stu;   // Student → User reference

        System.out.println("\n===== USER INFO =====");
        System.out.println(user.toString());
        System.out.println(user.role());

        System.out.println("\n===== EMPLOYEE INFO =====");
        System.out.println(emp.toString());
        System.out.println(emp.role());   // overridden method

        System.out.println("\n===== STUDENT INFO =====");
        System.out.println(stu.toString());
        System.out.println(stu.role());   // overridden method

        System.out.println("\n===== POLYMORPHISM OUTPUT =====");
        System.out.println(ref1.role());  // Employee role
        System.out.println(ref2.role());  // Student role
    }
}
```

---

# ⭐ Final Output Example

```
===== USER INFO =====
User Details:
Name: John Doe
Age: 30
Mobile: 1234567890
Address: New York
I am a general user.

===== EMPLOYEE INFO =====
User Details:
Name: Alice
Age: 28
Mobile: 9876543210
Address: California
Salary: 55000.0
I am an Employee and I earn $55000.0

===== STUDENT INFO =====
User Details:
Name: Bob
Age: 20
Mobile: 9998887777
Address: Texas
Course: Computer Science
I am a Student studying Computer Science

===== POLYMORPHISM OUTPUT =====
I am an Employee and I earn $55000.0
I am a Student studying Computer Science
```

---

# 🎉 Covers All OOP Concepts

| OOP Concept       | Used In                                              |
| ----------------- | ---------------------------------------------------- |
| **Class**         | User, Employee, Student                              |
| **Object**        | new User(), new Employee(), new Student()            |
| **Constructor**   | All classes                                          |
| **Encapsulation** | private fields + getters/setters                     |
| **Inheritance**   | Employee extends User, Student extends User          |
| **Polymorphism**  | overriding role(), User reference → Employee/Student |
| **toString()**    | For easy printing                                    |

---

If you want, I can also give:

✔ UML diagram
✔ Abstract classes example
✔ Interface example
✔ Multiple inheritance using interfaces

Just tell me!
