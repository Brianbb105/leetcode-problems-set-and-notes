# 1.XXX

## Pattern
Hashmap look for element, 

## Core idea
There will be a String List, and they are different elements, we have to sort them into anagrams and output the array seperately. 

Example:
- Given:
````
strs = ["eat","tea","tan","ate","nat","bat"]
````
- Output:
````
[["bat"],["nat","tan"],["ate","eat","tea"]]
````


## My Code
```java
class Solution {

    public List<List<String>> groupAnagrams(String[] strs) {
        HashMap<String, List<String>> groups = new HashMap<>();

        for (int i = 0; i < strs.length; i++) {
            String word = strs[i];

            int[] count = new int[26];

            for (int j = 0; j < word.length(); j++) {
                char c = word.charAt(j);
                count[c - 'a']++;
            }

            String key = Arrays.toString(count);

            groups.putIfAbsent(key, new ArrayList<>());
            groups.get(key).add(word);
        }

        return new ArrayList<>(groups.values());
    }

}
```

## What I got stuck on
-  
-
-

## Correct structure
```java

```


