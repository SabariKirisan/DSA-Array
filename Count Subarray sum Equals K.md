## Count Subarray sum Equals K (c++)

Given an array of integers nums and an integer k, return the total number of subarrays whose sum equals to k.

A subarray is a contiguous non-empty sequence of elements within an array.
## Example
Input: nums = [1,1,1], k = 2

Output: 2

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    int subarraySum(vector<int>& nums, int k) {
        int presum=0,cnt=0;
        int n=nums.size();
        unordered_map<int,int>mpp;
        mpp[0]=1;
        for(int i=0;i<n;i++)
        {
            presum+=nums[i];

            int remove=presum-k;

            cnt=cnt+mpp[remove];

            mpp[presum]+=1;
        }
        return cnt;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(N)

## OUTPUT
Output: 2
