## Single Number in array (c++)
Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

You must implement a solution with a linear runtime complexity and use only constant extra space.

Example 2:

Input: nums = [4,1,2,1,2]

Output: 4

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int n=nums.size();
        int xorr=0;
        for(int i=0;i<n;i++)
        {
            xorr=xorr^nums[i];
        }
        return xorr;
        
    }
};
```

## Complexity
- Time complexity : O(N)

- Space complexity : O(1)

## OUTPUT
Output: 4
