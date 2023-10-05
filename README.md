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
    boolean isTwoNumbersAddUpToK(ArrayList<Integer> numbers, Integer k) {

        ArrayList<Integer> listSeenElemenComplementNumToAddUpToK = new ArrayList<Integer>();
        
        for (Integer num : numbers) {
            Integer size = listSeenElemenComplementNumToAddUpToK.size();
            Integer lastSeenElementComplementNumToAddUpToK = null;
            if (size > 0) {
                lastSeenElementComplementNumToAddUpToK = listSeenElemenComplementNumToAddUpToK.get(size - 1);
            }
            
            if (num != lastSeenElementComplementNumToAddUpToK) {
                System.out.println(k + " = " + num + " + " + (k - num));
                return true;  
            }
            listSeenElemenComplementNumToAddUpToK.add(k - num);
        }
        return false;
    }

   /*
    *
    */
    public static void main(String[] args) {
        
        MyCodingProblemClass myClass = new MyCodingProblemClass();  
        
        ArrayList<Integer> numbers = new ArrayList<Integer>(Arrays.asList(10, 15, 3, 7));
        Integer k = 17;
    
        if (myClass.isTwoNumbersAddUpToK(numbers, k)) {
            System.out.println("Found");
        } else {
            System.out.println("Not Found");
        }
    }

    // Output
    // Success #stdin #stdout 0.17s 47224KB
    // 17 = 10 + 7
    // Found

    // I use this online compiler to run the above code
    // https://ideone.com/
}
```
