## Contains Duplicate (c++)

Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

## Example
Input: nums = [1,2,3,1]

Output: true

Explanation:

The element 1 occurs at the indices 0 and 3.

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) 
    {
        unordered_set<int> set;
        for(auto num:nums)
        {
            if(set.count(num))
            {
                return true;
            }
            set.insert(num);
        }
        return false;   
    }
};
```
## Complexity
- Time complexity : O(n)

- Space complexity : O(n)
