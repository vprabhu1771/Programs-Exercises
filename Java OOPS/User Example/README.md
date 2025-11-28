`User.java`
```java
public class User {
    private String name;
    private int age;
    private String mobile;
    private String address;

    public void setName(String n)
    {
        this.name = n;
    }

    public void getName()
    {
        System.out.println("Name : " + name);
    }
    
    public void setAge(int a)
    {
        this.age = a;
    }

    public void getAge()
    {
        System.out.println("age : " + age);
    }

    public void setMobileNo(String m)
    {
        this.mobile = m;
    }

    public void getMobileNo()
    {
        System.out.println("mobile : " + mobile);
    }

     public void setAddress(String a)
    {
        this.address = a;
    }

    public void getAddress()
    {
        System.out.println("address : " + address);
    }

}
```

`App.java`
```java
public class App{

    public static void main(String[] args) {
        
        User obj = new User();

        obj.setName("John Doe");
        obj.setAge(30);
        obj.setMobileNo("1234567890");
        obj.setAddress("123 Main Street New York City, NY 10001");

        System.out.println("====OUTPUT====");
        obj.getName();
        obj.getAge();
        obj.getMobileNo();
        obj.getAddress();        
    }
}
```