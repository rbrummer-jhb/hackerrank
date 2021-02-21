# Java String Tokens

Given a string, **_s_**, matching the regular expression [A-Za-z !,?._'@]+, split the string into tokens. We define a token to be one or more consecutive English alphabetic letters. Then, print the number of tokens, followed by each token on a new line.

**Note:** You may find the [String.split](https://docs.oracle.com/javase/8/docs/api/java/lang/String.html#split-java.lang.String-) method helpful in completing this challenge.

**Input Format**

A single string, **_s_**.

**Constraints**
* **_1 <= length of s <= 4.10^5_**
* **_s_** is composed of any of the following: English alphabetic letters, blank spaces, exclamation points (!), commas (,), question marks (?), periods (.), underscores (_), apostrophes ('), and at symbols (@).

**Output Format**

On the first line, print an integer, **_n_**, denoting the number of tokens in string **_s_** (they do not need to be unique). Next, print each of the **_n_** tokens on a new line in the same order as they appear in input string **_s_**.

**Sample Input**
```
He is a very very good boy, isn't he?
```

**Sample Output**
```
10
He
is
a
very
very
good
boy
isn
t
he
```

**Explanation**

We consider a token to be a contiguous segment of alphabetic characters. There are a total of **_10_** such tokens in string **_s_**, and each token is printed in the same order in which it appears in string **_s_**.

## Solution

```java
import java.io.*;
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        String s = scan.nextLine();
        
        // Write your code here.
        
        s = s.trim();
        String[] splitWords = s.split("[\\p{Punct}\\s]+");
        
        if (s.length() == 0) {
            scan.close();
            System.out.println(0);
        } else {
            System.out.println(splitWords.length);
            
            for (String word : splitWords){
                System.out.println(word);
            }
        
        scan.close();
    }
}
```
