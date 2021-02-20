# Java Loops I

**Objective**

In this challenge, we're going to use loops to help us do some simple math.

**Task**

Given an integer, **_N_**, print its first **_10_** multiples. Each multiple **_N x i_** (where **_1 <= i <= 10_**) should be printed on a new line in the form: `N x i = result`.

**Input Format**

A single integer, **_N_**.

**Constraints**

* **_2 <= N <= 20_**

**Output Format**

Print **_10_** lines of output; each line **_i_** (where **_1 <= i <= 10_**) contains the **_result_** of **_N x i_** in the form:

`N x i = result.`

**Sample Input**

```
2
```

**Sample Output**

```
2 x 1 = 2
2 x 2 = 4
2 x 3 = 6
2 x 4 = 8
2 x 5 = 10
2 x 6 = 12
2 x 7 = 14
2 x 8 = 16
2 x 9 = 18
2 x 10 = 20
```

## Solution

```java
import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.regex.*;

public class Solution {

    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        int N = scanner.nextInt();
        
        for (int i=1; i<11; i++) {
            System.out.printf("%d x %d = %d%n", N, i, N*i);
        }
        
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        scanner.close();
    }
}
```
