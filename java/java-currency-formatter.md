# Java Currency Formatter

Given a [double-precision](https://en.wikipedia.org/wiki/Double-precision_floating-point_format) number, **_payment_**, denoting an amount of money, use the [NumberFormat](https://docs.oracle.com/javase/8/docs/api/java/text/NumberFormat.html) class' [getCurrencyInstance](https://docs.oracle.com/javase/8/docs/api/java/text/NumberFormat.html#getCurrencyInstance-java.util.Locale-) method to convert **_payment_** into the US, Indian, Chinese, and French currency formats. Then print the formatted values as follows:
```
US: formattedPayment
India: formattedPayment
China: formattedPayment
France: formattedPayment
```

where **_formattedPayment_** is **_payment_** formatted according to the appropriate [Locale](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html)'s currency.

**Note:** India does not have a built-in Locale, so you must [construct one](https://docs.oracle.com/javase/8/docs/api/java/util/Locale.html#Locale-java.lang.String-java.lang.String-) where the language is en (i.e., English).

**Input Format**

A single double-precision number denoting **_payment_**.

**Constraints**
* **_0 <= payment <= 10^9_**

**Output Format**

On the first line, print US: u where **_u_** is **_payment_** formatted for US currency.
On the second line, print India: i where **_i_** is **_payment_** formatted for Indian currency.
On the third line, print China: c where **_c_** is **_payment_** formatted for Chinese currency.
On the fourth line, print France: f, where **_f_** is **_payment_** formatted for French currency.

**Sample Input**
```
12324.134
```

**Sample Output**
```
US: $12,324.13
India: Rs.12,324.13
China: ￥12,324.13
France: 12 324,13 €
```

**Explanation**

Each line contains the value of **_payment_** formatted according to the four countries' respective currencies.

## Solution

```java
import java.util.*;
import java.text.*;

public class Solution {
    
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        double payment = scanner.nextDouble();
        scanner.close();
        
        
        // Write your code here.
        
        String us = NumberFormat.getCurrencyInstance(Locale.US).format(payment);
        String india = NumberFormat.getCurrencyInstance(new Locale("EN", "IN")).format(payment);
        String china = NumberFormat.getCurrencyInstance(Locale.CHINA).format(payment);
        String france = NumberFormat.getCurrencyInstance(Locale.FRANCE).format(payment);
        
        
        System.out.println("US: " + us);
        System.out.println("India: " + india);
        System.out.println("China: " + china);
        System.out.println("France: " + france);
    }
}
```
