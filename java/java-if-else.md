# Java If-Else

In this challenge, we test your knowledge of using if-else conditional statements to automate decision-making processes. An if-else statement has the following logical flow:

![if-else-image](https://github.com/rbrummer-jhb/hackerrank/blob/main/java/images/if-else-image.png)

Wikipedia: [Source](https://en.wikipedia.org/wiki/Conditional_%28computer_programming%29)

**Task**

Given an integer, **_n_**, perform the following conditional actions:

* If **_n_** is odd, print `Weird`
* If **_n_** is even and in the inclusive range of **_2 to 5_** to , print `Not Weird`
* If **_n_** is even and in the inclusive range of **_6 to 20_** to , print `Weird`
* If **_n_** is even and greater than **_20_**, print `Not Weird`

Complete the stub code provided in your editor to print whether or not **_n_** is weird.

**Input Format**

A single line containing a positive integer, **_n_**.

**Constraints**

* **_1 <= n <= 100_**

**Output Format**

Print `Weird` if the number is weird; otherwise, print `Not Weird`.

**Sample Input 0**

```
3
```

**Sample Output 0**

```
Weird
```

**Sample Input 1**

```
24
```

**Sample Output 1**

```
Not Weird
```

**Explanation**

Sample Case 0: **_n = 3_**

**Sample Case 0:**

**_n_** is odd and odd numbers are weird, so we print `Weird`.

**Sample Case 1:**

Sample Case 1: **_n = 24_**

**_n > 20_** and **_n_** is even, so it isn't weird. Thus, we print `Not Weird`.

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
        scanner.skip("(\r\n|[\n\r\u2028\u2029\u0085])?");

        scanner.close();
        
        if ( N % 2 != 0 ) {
            System.out.println("Weird");
        } else if ( N % 2 == 0 && (N >= 2 && N <= 5) ) {
            System.out.println("Not Weird");
        } else if ( N % 2 == 0 && (N >= 6 && N <= 20) ) {
            System.out.println("Weird");
        } else {
            System.out.println("Not Weird");
        }
    }
}
```
