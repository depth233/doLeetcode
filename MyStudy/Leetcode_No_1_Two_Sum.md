title: "[Leetcode] No.1: Two Sum"
date: "2022-10-06 21:14:33"

Give an array of integers `nums` and an integer `target` , return indices of the two numbers such that they add up to `target`.<br>You may assume that each input would have **exactly one solution**, and you may not use the same element twice.<br>You can return the answer in any order.

**Example 1:**

```markdown
Input: nums = [2, 7, 11, 15], target = 9
Output: [0, 1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
```

**Example 2:**

```markdown
Input: nums = [3, 2, 4], target = 6
Output: [1, 2]
```

**Example 3:**

```markdown
Input: nums = [3, 3], target = 6
Output: [0, 1]
```

**Constraints:**

```markdown
· 2 <= nums.length <= 10^4
· -10^9 <= nums[i] <= 10^9
· -10^9 <= target <= 10^9
· Only one valid answer exists.
```

**Follow-up:** Can you come up with an algorithm that is less than `O(n^2)` time complexity?

### 一：暴力枚举

枚举数组中的每一个数 `x` ，并通过遍历数组查找是否存在 `target - x` 。

```c++
class solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
      int len = nums.size();
      for (int i = 0; i < len; ++i) {
        for(int j = i + 1; j < len; ++j) {
          if (nums[i] + nums[j] == target) {
            return {i, j};
          }
        }
      }
      return {};
    }
}
```

**复杂度分析**

时间复杂度为 $\theta (N^2)$ ：其中`N`是数组中的元素数量。最坏情况下数组中任意两个数都要被匹配一次。

空间复杂度为 $\theta (1)$ 。

> vector
