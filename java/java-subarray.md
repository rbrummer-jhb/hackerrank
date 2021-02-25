# Java Subarray

We define the following:
* A subarray of an **_n_**-element array is an array composed from a contiguous block of the original array's elements. For example, if **_array = [1, 2, 3]_**, then the subarrays are **_[1], [2], [3], [1, 2], [2, 3], and [1, 2, 3]_**. Something like  would not be a subarray as it's not a contiguous subsection of the original array.
* The sum of an array is the total sum of its elements.
  * An array's sum is negative if the total sum of its elements is negative.
  * An array's sum is positive if the total sum of its elements is positive.

Given an array of **_n_** integers, find and print its number of negative subarrays on a new line.

**Input Format**

The first line contains a single integer, **_n_**, denoting the length of array **_A = [ a[0], a[1], ..., a[n-1] ]_**.
The second line contains **_n_** space-separated integers describing each respective element, **_a[i]_**, in array **_A_**.

**Constraints**

* **_1 <= n <= 100_**
* **_-10^4 <= a[i] <= 10^4_**

**Output Format**

Print the number of subarrays of **_A_** having negative sums.

**Sample Input**
```
5
1 -2 4 -5 1
```

**Sample Output**
```
9
```

**Explanation**

There are nine negative subarrays of **_A = [1, -2, 4, -5, 1]_**:
1. **_[1 : 1]  ->  -2_**
2. **_[3 : 3]  ->  -5_**
3. **_[0 : 1]  ->  1 + -2 = -1_**
4. **_[2 : 3]  ->  4 + -5 = -1_**
5. **_[3 : 4]  ->  -5 + 1 = -4_**
6. **_[1 : 3]  ->  -2 + 4 + -5 = -2_**
7. **_[0 : 3]  ->  1 + -2 + 4 + -5 = -2_**
8. **_[1 : 4]  ->  -2 + 4 + -5 + 1 = -2_**
9. **_[0 : 4]  ->  1 + -2 + 4 + -5 + 1 = -1_**

Thus, we print **_9_** on a new line.

## Solution (Incomplete)

```
import java.io.*;
import java.util.*;
import java.text.*;
import java.math.*;
import java.util.regex.*;

public class Solution {

    public static void main(String[] args) {
        /* 
        ** Enter your code here. Read input from STDIN.
        ** Print output to STDOUT. Your class should be named Solution. 
        */
```
```java
        Scanner scanner = new Scanner(System.in);
        int arrSize = scanner.nextInt();
        int[] numbers = new int[arrSize];
        int count = 0;
        
        for (int i = 0; i < scanner.nextInt(); i++) {
            numbers[i] = scanner.nextInt();
        }
        // System.out.println(Arrays.toString(numbers));
        
        for (int i = 0; i < arrSize; i++) {
            for (int j = 1; j < arrSize; j++) {
                if ( (numbers[i] + numbers[j]) < 0) {
                    count++;
                }
                else if ( (i < arrSize) && (numbers[i] + numbers[i + 1]) < 0 ) {
                    count++;
                }
            }
        }
        System.out.println(count);
```
```
    }
}
```
