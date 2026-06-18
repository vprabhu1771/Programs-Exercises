```java
class Box {
    int a, b;
    void multi(Box obj) {
        System.out.print(obj.a + " * " + obj.b + " = ");
        System.out.println(obj.a * obj.b);
    }
}

public class app {
    static void main() {
        Box obj = new Box();
        Box test = new Box();
        test.a = 2;
        test.b = 3;
        obj.multi(test);

    }
}
```

```
2 * 3 = 6
```
