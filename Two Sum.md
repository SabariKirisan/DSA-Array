## Two Sum (c++)

Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.
## Example
Input: nums = [2,7,11,15], target = 9

Output: [0,1]

Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) 
    {
        int n=nums.size();

        unordered_map<int,int> mpp;

        for(int i=0;i<n;i++)
        {
            int sum=nums[i];

            int needed=target-sum;

            if(mpp.find(needed)!=mpp.end())
            {
                return {mpp[needed],i};
            }
            mpp[sum]=i;
        }
        return {-1,-1};
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(N)

## OUTPUT
Output: [0,1]
