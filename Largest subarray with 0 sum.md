## Largest subarray with 0 sum (c++)

Given an array arr containing both positive and negative integers, the task is to compute the length of the largest subarray that has a sum of 0.
## Example
Input: arr[] = [15, -2, 2, -8, 1, 7, 10, 23]

Output: 5

Explanation: The largest subarray with a sum of 0 is [-2, 2, -8, 1, 7].

## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    int maxLen(vector<int>& arr) {
        
        unordered_map<int,int> mpp;
        int n=arr.size();
        int sum=0;
        int maxi=0;
        for(int i=0;i<n;i++)
        {
            sum+=arr[i];
            
            if(sum==0)
            {
                maxi=i+1;
            }
            else
            {
                if(mpp.find(sum)!=mpp.end())
                {
                    maxi=max(maxi,i-mpp[sum]);
                }
                else
                {
                    mpp[sum]=i;
                }
            }
        }
        return maxi;
    }
};

```
## Complexity
- Time complexity : O(N)

- Space complexity : O(N)

## OUTPUT
Output: 5
