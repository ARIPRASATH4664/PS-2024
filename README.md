# PS-2024

<details>
  <summary> Contains Duplicate</summary>

**Question**
```
Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

Example 1:

Input: nums = [1,2,3,1]
Output: true
Example 2:

Input: nums = [1,2,3,4]
Output: false
Example 3:

Input: nums = [1,1,1,3,3,4,3,2,4,2]
Output: true
 

Constraints:

1 <= nums.length <= 105
-109 <= nums[i] <= 109
```
**Solution**
```
var containsDuplicate = function(nums) {
    const track = {}
    for (item of nums) {
        if(track[item]) {
            return true
        } else {
            track[item] = true;
        }
    }
    return false;
};
```

</details>



<details>
  <summary> Valid Anagram</summary>

## Question
```
Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

 

Example 1:

Input: s = "anagram", t = "nagaram"
Output: true
Example 2:

Input: s = "rat", t = "car"
Output: false
 

Constraints:

1 <= s.length, t.length <= 5 * 104
s and t consist of lowercase English letters.
 

Follow up: What if the inputs contain Unicode characters? How would you adapt your solution to such a case?
```

## Solution

```
/**
 * @param {string} s
 * @param {string} t
 * @return {boolean}
 */
var isAnagram = function(s, t) {
    const temp = {}

    if(s.length === t.length &&  s.length > 0){
        for( char of s) {
            if(temp[char]) {
                temp[char] = (temp[char] + 1);
            } else {
                temp[char] = 1; 
            }
        }

        for(char of t) {
            if(temp[char] >= 1) {
                if(temp[char] === 1) {
                    delete temp[char];
                } else {
                    temp[char] = (temp[char] - 1);
                }
            } else {
                return false
            }
        }
        return true
    }

    return false;

};
```
</details>
