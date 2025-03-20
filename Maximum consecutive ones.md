## find Max Consecutive Ones (c++)
Given a binary array nums, return the maximum number of consecutive 1's in the array.

Input: nums = [1,1,0,1,1,1]

Output: 3

Explanation: The first two digits or the last three digits are consecutive 1s. The maximum number of consecutive 1s is 3.

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    int findMaxConsecutiveOnes(vector<int>& nums) {
        int n=nums.size();
        int cnt=0;
        int total=0;
        for(int i=0;i<n;i++)
        {
            if(nums[i]==1)
            {
                cnt++;
                total=max(total,cnt);
            }
            else
            {
                cnt=0;
            }
        }
        return total;
        
    }
};
```

## Complexity
- Time complexity : O(N)

- Space complexity : O(1)

## OUTPUT
Output: 3
