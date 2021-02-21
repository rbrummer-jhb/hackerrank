# Java Substring

Given a string, **_s_**, and two indices, **_start_** and **_end_**, print a substring consisting of all characters in the inclusive range from **_start_** to **_end - 1_**. You'll find the String class' substring method helpful in completing this challenge.

**Input Format**

The first line contains a single string denoting **_s_**.
The second line contains two space-separated integers denoting the respective values of **_start_** and **_end_**.

**Constraints**

String **_s_** consists of English alphabetic letters (i.e., **_[a-zA-Z]_**) only.

**Output Format**

Print the substring in the inclusive range from **_start_** to **_end - 1_**.

**Sample Input**
```
Helloworld
3 7
```

**Sample Output**
```
lowo
```

**Explanation**

In the diagram below, the substring is highlighted in green:

![substring-image]()

## Solution

```java
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        String S = in.next();
        int start = in.nextInt();
        int end = in.nextInt();
        
        // Write your code here
        
        System.out.println(S.substring(start,end));
    }
}
```
