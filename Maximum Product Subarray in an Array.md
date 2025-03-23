## Maximum Product Subarray in an Array (c++)

Given an integer array nums, find a subarray that has the largest product, and return the product.

The test cases are generated so that the answer will fit in a 32-bit integer.
## Example
Input: nums = [2,3,-2,4]

Output: 6

Explanation: [2,3] has the largest product 6.

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    int maxProduct(vector<int>& nums) {

        int n=nums.size();
        int ans=INT_MIN;
        int prefix=1,suffix=1;
        for(int i=0;i<n;i++)
        {
            if(prefix==0) prefix=1;
            if(suffix==0) suffix=1;
            
            prefix=prefix*nums[i];
            suffix=suffix*nums[n-i-1];
            ans=max(ans,max(prefix,suffix));
        }
        return ans;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)

## OUTPUT
Output: 6
