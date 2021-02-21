# Java Date and Time

The [Calendar class](https://docs.oracle.com/javase/7/docs/api/java/util/Calendar.html) is an abstract class that provides methods for converting between a specific instant in time and a set of calendar fields such as YEAR, MONTH, DAY_OF_MONTH, HOUR, and so on, and for manipulating the calendar fields, such as getting the date of the next week.

You are given a date. You just need to write the method, **_getDay_**, which returns the day on that date. To simplify your task, we have provided a portion of the code in the editor.

For example, if you are given the date **_August 14th 2017_**, the method should return **_MONDAY_** as the day on that date.

![calendar-image](https://github.com/rbrummer-jhb/hackerrank/blob/main/java/images/calendar-image.png)

**Input Format**

A single line of input containing the space separated month, day and year, respectively, in **_MM DD YYYY_** format.

**Constraints**

* 2000 < year < 3000

**Output Format**

Output the correct day in capital letters.

**Sample Input**
```
08 05 2015
```

**Sample Output**
```
WEDNESDAY
```

**Explanation**

The day on August **_5th 2015_**  was WEDNESDAY.

## Solution

```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

class Result {

    /*
     * Complete the 'findDay' function below.
     *
     * The function is expected to return a STRING.
     * The function accepts following parameters:
     *  1. INTEGER month
     *  2. INTEGER day
     *  3. INTEGER year
     */

    public static String findDay(int month, int day, int year) {
        
        // Write your code here
        
        Calendar calObject = Calendar.getInstance();
        calObject.set(Calendar.MONTH, month-1);
        calObject.set(Calendar.DAY_OF_MONTH, day);
        calObject.set(Calendar.YEAR, year);
        
        return calObject.getDisplayName(Calendar.DAY_OF_WEEK, Calendar.LONG, Locale.getDefault()).toUpperCase();
    }
}


public class Solution {

    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));
        BufferedWriter bufferedWriter = new BufferedWriter(new FileWriter(System.getenv("OUTPUT_PATH")));

        String[] firstMultipleInput = bufferedReader.readLine().replaceAll("\\s+$", "").split(" ");

        int month = Integer.parseInt(firstMultipleInput[0]);

        int day = Integer.parseInt(firstMultipleInput[1]);

        int year = Integer.parseInt(firstMultipleInput[2]);

        String res = Result.findDay(month, day, year);

        bufferedWriter.write(res);
        bufferedWriter.newLine();

        bufferedReader.close();
        bufferedWriter.close();
    }
}
```
