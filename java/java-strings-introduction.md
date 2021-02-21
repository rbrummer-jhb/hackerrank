# Java Strings Introduction

> "A string is traditionally a sequence of characters, either as a literal constant or as some kind of variable." — [Wikipedia: String (computer science)](https://en.wikipedia.org/wiki/String_%28computer_science%29)

This exercise is to test your understanding of Java Strings. A sample String declaration:
```
String myString = "Hello World!"
```

The elements of a String are called characters. The number of characters in a String is called the length, and it can be retrieved with the String.length() method.

Given two strings of lowercase English letters, **_A_** and **_B_**, perform the following operations:

1. Sum the lengths of **_A_** and **_B_**.
2. Determine if **_A_** is lexicographically larger than **_B_** (i.e.: does **_B_** come before **_A_** in the dictionary?).
3. Capitalize the first letter in **_A_** and **_B_** and print them on a single line, separated by a space.

**Input Format**

The first line contains a string . The second line contains another string . The strings are comprised of only lowercase English letters.

**Output Format**

There are three lines of output:
For the first line, sum the lengths of **_A_** and **_B_**.
For the second line, write Yes if **_A_** is lexicographically greater than **_B_** otherwise print `No` instead.
For the third line, capitalize the first letter in both **_A_** and **_B_** and print them on a single line, separated by a space.

**Sample Input 0**
```
hello
java
```

**Sample Output 0**
```
9
No
Hello Java
```

**Explanation 0**

String **_A_** is "hello" and **_B_** is "java".

**_A_** has a length of , and **_B_** has a length of **_4_**; the sum of their lengths is **_9_**.
When sorted alphabetically/lexicographically, "hello" precedes "java"; therefore, **_A_** is not greater than **_B_** and the answer is `No`.

When you capitalize the first letter of both **_A_** and **_B_** and then print them separated by a space, you get "Hello Java".

## Solution

```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        
        Scanner sc=new Scanner(System.in);
        String A=sc.next();
        String B=sc.next();
        /* Enter your code here. Print output to STDOUT. */
        
        int sum = A.length() + B.length();
        
        String wordA = A.substring(0,1).toUpperCase() + A.substring(1);
        String wordB = B.substring(0,1).toUpperCase() + B.substring(1);
        
        System.out.println(sum);
        
        if ( A.compareTo(B) > B.compareTo(A) ) {
            System.out.println("Yes");
        } else {
            System.out.println("No");
        }
        
        System.out.println( wordA + " " + wordB );
    }
}
```
