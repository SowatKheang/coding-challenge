# coding-challenge

### Problem 1
```
This problem was asked by Google.

Given a list of numbers and a number k, return whether any two numbers from the list add up to k.

For example, given [10, 15, 3, 7] and k of 17, return true since 10 + 7 is 17.

```
#### Solution to Problem 1 in JAVA
```java
import java.util.*;

class MyCodingProblemClass {

   /*
    *
    */
     boolean isTwoNumbersAddUpToK(int[] numbers, int k) {
        HashSet<Integer> listSeenElementComplementNumAddUpToK = new HashSet<Integer>();
        for (int num : numbers) {
            int complementNumAddUpToK = k - num;
            if (listSeenElementComplementNumAddUpToK.contains(complementNumAddUpToK)) {
                System.out.println(k + " = " + num + " + " + complementNumAddUpToK);
                return true;
            }
            listSeenElementComplementNumAddUpToK.add(num);
        }
        return false;
    }
 
   /*
    *
    */
    public static void main(String[] args) {
 
        MyCodingProblemClass myClass = new MyCodingProblemClass();  
 
        int[] numbers = {10, 15, 3, 7};
        int k = 17;
 
        if (myClass.isTwoNumbersAddUpToK(numbers, k)) {
            System.out.println("Found");
        } else {
            System.out.println("Not Found");
        }
    }

    // Output
    // Success #stdin #stdout 0.15s 48596KB
    // stdout copy
    // 17 = 7 + 10
    // Found

    // I use this online compiler to run the above code
    // https://ideone.com/
}
```
