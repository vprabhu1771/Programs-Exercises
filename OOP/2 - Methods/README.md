```
import java.util.Scanner;

class DateOfBirth {
    int date,month,year;

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
        DateOfBirth abi = new DateOfBirth();
        abi.setDob(3,8,1992);        
        abi.getDob();
    }
}
