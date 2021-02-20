# Java Loops II

We use the integers **_a, b,_** and **_n_** to create the following series:

**_(a + 2^0 * b), (a + 2^0 * b + 2^1 * b), ...,(a + 2^0 * b + 2^1 * b + ... + 2^n-1 * b)_**

You are given **_q_** queries in the form of **_a, b,_** and **_n_**. For each query, print the series corresponding to the given **_a, ,b_** and **_n_** values as a single line of **_n_** space-separated integers.

**Input Format**

The first line contains an integer, **_q_**, denoting the number of queries.
Each line **_i_** of the **_q_** subsequent lines contains three space-separated integers describing the respective **_a[i], b[i],_** and **_n[i]_** values for that query.

**Constraints**

* **_0 <= q <= 500_**
* **_0 <= a, b <= 50_**
* **_1 <= n <= 15_**

**Output Format**

For each query, print the corresponding series on a new line. Each series must be printed in order as a single line of **_n_** space-separated integers.

**Sample Input**

```
2
0 2 10
5 3 5
```

**Sample Output**

```
2 6 14 30 62 126 254 510 1022 2046
8 14 26 50 98
```

**Explanation**

We have two queries:

1. We use **_a = 0, b = 2,_** and **_n = 10_** to produce some series **_s[0], s[1], ..., s[n-1]_**:
* **_s[0] = 0 + 1 * 2 = 2_**
* **_s[1] = 0 + 1 * 2 + 2 * 2 = 6_**
* **_s[2] = 0 + 1 * 2 + 2 * 2 + 4 * 2 = 14_**

... and so on.

Once we hit **_n = 10_**, we print the first ten terms as a single line of space-separated integers.

2. We use **_a = 5, b = 3,_** and **_n = 5_** to produce some series **_s[0], s[1], ..., s[n-1]_**:
* **_s[0] = 1 * 3 = 8_**
* **_s[1] = 1 * 3 + 2 * 3 = 14_**
* **_s[2] = 1 * 3 + 2 * 3 + 4 * 3 = 26_**
* **_s[3] = 1 * 3 + 2 * 3 + 4 * 3 + 8 * 3 = 50_**
* **_s[4] = 1 * 3 + 2 * 3 + 4 * 3 + 8 * 3 + 16 * 3 = 98_**

We then print each element of our series as a single line of space-separated values.

## Solution

```java
import java.util.*;
import java.io.*;

class Solution{
    public static void main(String []argh){
        Scanner in = new Scanner(System.in);
        int t=in.nextInt();
        for(int i=0;i<t;i++){
            int a = in.nextInt();
            int b = in.nextInt();
            int n = in.nextInt();
            
            for (int j=0; j<n; j++) {
                a += Math.pow(2,j) * b;
                System.out.printf("%d ",a);
            }
            System.out.printf("%n");
        }
        in.close();
    }
}
```
