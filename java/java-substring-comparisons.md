# Java Substring Comparisons

We define the following terms:

* [Lexicographical Order](https://en.wikipedia.org/wiki/Lexicographic_order), also known as alphabetic or dictionary order, orders characters as follows:
  
  **_A < B < ... < Y < Z < a < b < ... < y < z_**
  
  For example, ball < cat, dog < dorm, Happy < happy, Zoo < ball.

* A [substring](https://en.wikipedia.org/wiki/Substring) of a string is a contiguous block of characters in the string. For example, the substrings of abc are a, b, c, ab, bc, and abc.

Given a string, **_s_**, and an integer, **_k_**, complete the function so that it finds the lexicographically smallest and largest substrings of length **_k_**.

**Input Format**

The first line contains a string denoting **_s_**.
The second line contains an integer denoting **_k_**.

**Constraints**
* **_1 <= |s| <= 1000_**
* **_s_** consists of English alphabetic letters only (i.e., [a-zA-Z]).

**Output Format**

Return the respective lexicographically smallest and largest substrings as a single newline-separated string.

**Sample Input 0**
```
welcometojava
3
```

**Sample Output 0**
```
ava
wel
```

**Explanation 0**

String **_s = "welcometojava_** has the following lexicographically-ordered substrings of length **_k = 3_**:

**_["ava", "come", "elc", "eto", "jav", "lco", "met", "oja", "ome", "toj", "wel"]_**

We then return the first (lexicographically smallest) substring and the last (lexicographically largest) substring as two newline-separated values (i.e., ava\nwel).

The stub code in the editor then prints ava as our first line of output and wel as our second line of output.

## Solution

```java
import java.util.Scanner;

public class Solution {

    public static String getSmallestAndLargest(String s, int k) {
        String smallest = "";
        String largest = "";
        
        // Complete the function
        // 'smallest' must be the lexicographically smallest substring of length 'k'
        // 'largest' must be the lexicographically largest substring of length 'k'
        
        smallest = s.substring(0, k);
        largest = smallest;
        String temp = "";
        
        for (int i = 0; i <= s.length() - k; i++) {
            temp = s.substring(i, i + k);
            
            if (temp.compareTo(smallest) < 0) {
                smallest = temp;
            } else if (temp.compareTo(largest) > 0) {
                largest = temp;
            }
        }
        
        return smallest + "\n" + largest;
    }


    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        String s = scan.next();
        int k = scan.nextInt();
        scan.close();
      
        System.out.println(getSmallestAndLargest(s, k));
    }
}
```
