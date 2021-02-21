# Java String Reverse

```
A palindrome is a word, phrase, number, or other sequence of characters which reads the same backward or forward.(Wikipedia)
```

Given a string **_A_**, print Yes if it is a palindrome, print `No` otherwise.

**Constraints**

* **_A_** will consist at most **_50_** lower case english letters.

**Sample Input**

```
madam
```

**Sample Output**

```
Yes
```

## Solution

```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        
        Scanner sc=new Scanner(System.in);
        String A=sc.next();
        /* Enter your code here. Print output to STDOUT. */
        
        String B = "";
        
        for (int i = A.length() - 1; i >= 0; i--) {
            B = (B + A.charAt(i));
        }
        
        if (A.compareToIgnoreCase(B) == 0) {
            System.out.println("Yes");
        } else {
            System.out.println("No");
        }
    }
}
```
