# Java Static Initializer Block

Static initialization blocks are executed when the class is loaded, and you can initialize static variables in those blocks.

It's time to test your knowledge of Static initialization blocks. You can read about it [here](https://docs.oracle.com/javase/tutorial/java/javaOO/initial.html).

You are given a class Solution with a main method. Complete the given code so that it outputs the area of a parallelogram with breadth **_B_** and height **_H_**. You should read the variables from the standard input.

If **_B <= 0_** or **_H <= 0_**, the output should be "java.lang.Exception: Breadth and height must be positive" without quotes.

**Input Format**

There are two lines of input. The first line contains **_B_**: the breadth of the parallelogram. The next line contains **_H_**: the height of the parallelogram.

**Constraints**

* **_-100 <= B <= 100_**
* **_-100 <= H <= 100_**

**Output Format**

If both values are greater than zero, then the main method must output the area of the parallelogram. Otherwise, print "java.lang.Exception: Breadth and height must be positive" without quotes.

**Sample input 1**
```
1
3
```

**Sample output 1**
```
3
```

**Sample input 2**
```
-1
2
```

**Sample output 2**
```
java.lang.Exception: Breadth and height must be positive
```

## Solution
```java
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

  // Write your code here

  static Scanner scanner = new Scanner(System.in);
  static int B = scanner.nextInt();
  static int H = scanner.nextInt();

  public static boolean checkNumbers() {
      try {
          if (B > 0 && H > 0) {
              return true;
          } else {
              throw new Exception("Breadth and height must be positive");
          }
      } catch (Exception e) {
          System.out.println(e);
          return false;
      }
  }

  static boolean flag = checkNumbers();

  public static void main(String[] args) {
      if (flag) {
          int area=B*H;
          System.out.print(area);
      }
		
  }//end of main

}//end of class
