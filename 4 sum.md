## 4 Sum | Find Quads that add up to a target value (c++)

Given an array nums of n integers, return an array of all the unique quadruplets [nums[a], nums[b], nums[c], nums[d]] such that:

0 <= a, b, c, d < n

a, b, c, and d are distinct.

nums[a] + nums[b] + nums[c] + nums[d] == target

You may return the answer in any order.
## Example
Input: nums = [1,0,-1,0,-2,2], target = 0

Output: [[-2,-1,1,2],[-2,0,0,2],[-1,0,0,1]]

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    vector<vector<int>> fourSum(vector<int>& nums, int target) {

        sort(nums.begin(),nums.end());
        vector<vector<int>>ans;
        int n=nums.size();
        for(int i=0;i<n;i++)
        {
            if(i>0 && nums[i]==nums[i-1]) continue;

            for(int j=i+1;j<n;j++)
            {
                if(j!=i+1 && nums[j]==nums[j-1]) continue;
                int k=j+1;
                int l=n-1;

                while(k<l)
                {
                    long long sum=nums[i];
                    sum+=nums[j];
                    sum+=nums[k];
                    sum+=nums[l];
                    if(sum==target)
                    {
                        ans.push_back({nums[i],nums[j],nums[k],nums[l]});
                        k++;
                        l--;
                        while(k<l && nums[k]==nums[k-1]) k++;
                        while(k<l && nums[l]==nums[l+1]) l--;  
                    }
                    else if(sum>target) l--;
                    else k++;
                }
            }
        }
        return ans;
        
    }
};
```
## Complexity
- Time complexity : O(N^3)

- Space complexity : O(1)

## OUTPUT
Output: [[-2,-1,1,2],[-2,0,0,2],[-1,0,0,1]]
