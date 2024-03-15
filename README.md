# PS-2024

## Array & Hashing

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


<details>
  <summary>Two Sum</summary>

## Question
```
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

 

Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]
Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]
 

Constraints:

2 <= nums.length <= 104
-109 <= nums[i] <= 109
-109 <= target <= 109
Only one valid answer exists.
 

Follow-up: Can you come up with an algorithm that is less than O(n2) time complexity?
```

  ## Solution
  ```
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    const hash = {};
    for( index in nums) {
        let diff = target - nums[index];
        if(hash[diff]) {
            return [hash[diff], index]
        } else {
            hash[nums[index]] = index
        }
    }
    return []
};
```
</details>
