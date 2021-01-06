# 1. Two Sum

Given an array of integers `nums` and an integer `target`, return _indices of the two numbers such that they add up to `target`_.

You may assume that each input would have _**exactly**_ **one solution**, and you may not use the _same_ element twice.

You can return the answer in any order.

**Example 1:**

```text
Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Output: Because nums[0] + nums[1] == 9, we return [0, 1].
```

**Example 2:**

```text
Input: nums = [3,2,4], target = 6
Output: [1,2]
```

**Example 3:**

```text
Input: nums = [3,3], target = 6
Output: [0,1]
```

**Constraints:**

* `2 <= nums.length <= 103`
* `-109 <= nums[i] <= 109`
* `-109 <= target <= 109`
* **Only one valid answer exists.**

\*\*\*\*

```text
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
      
      Hashtable h_table = new Hashtable();
      
      for(int i = 0; i < nums.Length; i++){
        if(h_table.ContainsKey(target - nums[i])){
          return new int[2] {(int)h_table[target - nums[i]], i};
        }
        else if(!h_table.ContainsKey(nums[i])){
          h_table.Add(nums[i],i);
        }
      }
      return new int[2];
    }
}
```

