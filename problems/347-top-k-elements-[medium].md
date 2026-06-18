
# 347. Top K Elements 

## Pattern
HashMap again
Some built in, sorting the map key and count

## Core idea
So basically you have to find out the top k element in the int array. 


Example:
- Input: nums = [1,1,1,2,2,3], k = 2
- Output: [1,2]




## My Code
```java
import java.util.*;

class Solution {
    public int[] topKFrequent(int[] nums, int k) {
        HashMap<Integer, Integer> map = new HashMap<>();

        // 1. Count frequency
        for (int num : nums) { //enhanced for loop
            //equivalent to 
            //for (int i = 0; i < nums.length; i++) {
            //int num = nums[i];
            // }
            map.put(num, map.getOrDefault(num, 0) + 1);
        }

        // 2. Put all unique numbers into a list
        List<Integer> list = new ArrayList<>(map.keySet());
        //map.keySet() gets the keys in the map

        // 3. Sort by frequency from high to low
        Collections.sort(list, (a, b) -> map.get(b) - map.get(a));
        //lamda expression, which is sorting the array list we created before
        //by using the built-in Collection.sort(list, xxx)

        // 4. Take the first k elements
        int[] result = new int[k];

        for (int i = 0; i < k; i++) {
            result[i] = list.get(i);
        }

        return result;
    }
}
```

## What I got stuck on
-  I got stuck on how to get the top k element in this int array
- It is more of like it is easy to get the value and the key, but hard to get to top elements
-

## Correct structure
```java
Collections.sort(list, (a, b) -> map.get(b) - map.get(a));
//The lambda sort

List<Integer> list = new ArrayList<>(map.keySet());
//Gets all the keys (elements in the map)

for (int num : nums){}
//enhanced for loop, equivalent to 
        for (int i = 0; i < nums.length; i++) {
        int num = nums[i];
        }
```

