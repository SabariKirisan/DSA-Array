## Kadane's Algorithm : Maximum Subarray Sum in an Array (c++)

Given an integer array nums, find the subarray with the largest sum, and return its sum.
## Example
Input: nums = [-2,1,-3,4,-1,2,1,-5,4]

Output: 6

Explanation: The subarray [4,-1,2,1] has the largest sum 6.

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    int maxSubArray(vector<int>& nums) 
    {
        int n=nums.size();
        int sum=0;
        int maxi=INT_MIN;

        //int ans_start=-1,ans_end=-1;

        for(int i=0;i<n;i++)
        {
           // if(sum==0) int start=i;
            sum=sum+nums[i];

            if(sum>maxi)
            {
                maxi=sum;
                //ans_start=start,ans_end=i;
            }
            if(sum<0)
            {
                sum=0;
            }
        }
        return maxi;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)

## OUTPUT
Output: 6
