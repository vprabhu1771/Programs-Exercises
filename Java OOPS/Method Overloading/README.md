```
class Box {

    void multi() {
        System.out.println("No Values to Multiply");

    }

    void multi(int a) {
        System.out.print(a + " * " + a + " : ");
        System.out.println(a * a);
    }

    void multi(int a, int b) {
        System.out.print(a + " * " + b + " : ");
        System.out.println(a * b);
    }

    double multi(double a) {
        return a * a;

    }

}
public class app {
    static void main(String[] args) {
        Box obj = new Box();

        double result;
        obj.multi();
        obj.multi(10);
        obj.multi(10, 20);
        result = obj.multi(2.0);
        System.out.println("Result : " + result);
    }

}
```
