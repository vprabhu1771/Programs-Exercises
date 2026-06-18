```java
class Box {
    void multi(int a) {
        System.out.print(a + " * " + a + " = ");
        System.out.println(a * a);
    }
}

public class app {
    static void main() {
        Box obj = new Box();
        obj.multi(8);
    }
}
```

```
8 * 8 = 64
```
