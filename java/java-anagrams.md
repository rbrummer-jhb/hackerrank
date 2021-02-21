# Java Anagrams

Two strings, **_a_** and **_b_**, are called anagrams if they contain all the same characters in the same frequencies. For example, the anagrams of CAT are CAT, ACT, TAC, TCA, ATC, and CTA.

Complete the function in the editor. If **_a_** and **_b_** are case-insensitive anagrams, print "Anagrams"; otherwise, print "Not Anagrams" instead.

**Input Format**

The first line contains a string denoting **_a_**.
The second line contains a string denoting **_b_**.

**Constraints**

* **_1 <= length(a), length(b) <= 50_**
* Strings  and  consist of English alphabetic characters.
* The comparison should NOT be case sensitive.

**Output Format**

Print "Anagrams" if **_a_** and **_b_** are case-insensitive anagrams of each other; otherwise, print "Not Anagrams" instead.

**Sample Input 0**
```
anagram
margana
```

**Sample Output 0**
```
Anagrams
```

**Explanation 0**

| Character	| Frequency: anagram | Frequency: margana |
| --------- | ------------------ | ------------------ |
| A or a | 3 | 3 |
| G or g | 1 | 1 |
| N or n | 1 | 1 |
| M or m | 1 | 1 |
| R or r | 1 | 1 |

The two strings contain all the same letters in the same frequencies, so we print "Anagrams".

**Sample Input 1**
```
anagramm
marganaa
```

**Sample Output 1**
```
Not Anagrams
```

**Explanation 1**

| Character	Frequency: | anagramm	Frequency: | marganaa |
| -------------------- | ------------------- | -------- |
| A or a | 3 | 4 |
| G or g | 1 | 1 |
| N or n | 1 | 1 |
| M or m | 2 | 1 |
| R or r | 1 | 1 |

The two strings don't contain the same number of a's and m's, so we print "Not Anagrams".

**Sample Input 2**
```
Hello
hello
```

**Sample Output 2**
```
Anagrams
```

**Explanation 2**

| Character |	Frequency: Hello | Frequency: hello |
| --------- | ---------------- | ---------------- |
| E or e | 1 | 1 |
| H or h | 1 | 1 |
| L or l | 2 | 2 |
| O or o | 1 | 1 |

The two strings contain all the same letters in the same frequencies, so we print "Anagrams".

## Solution

```java
import java.util.Scanner;

public class Solution {

    static int  countChar(char a, String s){
        int count = 0;
        for(int i = 0; i < s.length() ; i++)
        {
            if(s.charAt(i) == a)
                count++;
        }
        // System.out.printf("count_val %d", count);
        return count;
    }
    static boolean isAnagram(String a, String b) {
        // Complete the function
        // alphabet 
        
        char[] found_chars = new char[26];
        int frequency_A = 0;
        int frequency_B = 0;
        char temp_l_holder = ' ';
        
        // go through the a string first
        // a.equals(b)
        
        if (a.length() != b.length())
            return false;
        int c_found = 0;
        a = a.toLowerCase();
        b = b.toLowerCase();
        
        for(int index_a = 0; index_a < a.length(); index_a++){
            temp_l_holder = a.charAt(index_a);
            
            if (new String(found_chars).indexOf(temp_l_holder) != -1){
                continue;
            }
            
            if (countChar(temp_l_holder, a) != countChar(temp_l_holder, b))
            {
                return false;
                // System.out.printf("dont match %c", temp_l_holder);
            }
            found_chars[c_found] = temp_l_holder;
        }
        return true;
    }    
    

    public static void main(String[] args) {
    
        Scanner scan = new Scanner(System.in);
        String a = scan.next();
        String b = scan.next();
        scan.close();
        boolean ret = isAnagram(a, b);
        System.out.println( (ret) ? "Anagrams" : "Not Anagrams" );
    }
}
```
