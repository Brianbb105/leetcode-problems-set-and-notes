# 169. Majority Element

## Pattern
HashMap

## Core idea
Find the most repeated element in the integer array. 
Most repeated is defined by number of repeat > num.length  / 2

Example:
- [3,2,3] should return 3
- [2,2,1,1,1,2,2] should return 2

## My Code
```java
public int majorityElement(int[] nums) {

    HashMap<Integer, Integer> map = new HashMap<>();
    //First Integer is the element, and the second is the count

    for (int i = 0; i < nums.length; i ++){
        int a = nums[i];
        int count = map.getOrDefault(a,0) +1;
        map.put(a,count);

        if (count > nums.length / 2){
            return a;
        }
    }

    return -1;

}
```

## What I got stuck on
- First I didn't see "The majority element is the element that appears more than ⌊n / 2⌋ times." part in the description, so I considered many cases that are not necessary. 
- Logic-wise also, I was thinking so much when solving this problem, so that if loop didn't come to my mind at all. 

## Correct structure
```java
Map<Integer, Integer> map = new HashMap<>();
```
