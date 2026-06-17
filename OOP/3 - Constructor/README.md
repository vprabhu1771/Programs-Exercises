```
import java.util.Scanner;

class DateOfBirth {
    int date,month,year;

    DateOfBirth() {}

    DateOfBirth(int d, int m, int y)
    {
        date = d;
        month = m;
        year = y;
    }

    void setDob(int d, int m, int y)
    {
        date = d;
        month = m;
        year = y;
    }

    void getDob()
    {
        System.out.println(date+ "-" + month + "-" + year);
    }
}

public class app
{
    public static void main(String[] args) {
        DateOfBirth abi = new DateOfBirth(3,8,1992);
        DateOfBirth ram = new DateOfBirth();

        ram.setDob(23,3,1990);

        abi.getDob();
        ram.getDob();
    }
}
```
