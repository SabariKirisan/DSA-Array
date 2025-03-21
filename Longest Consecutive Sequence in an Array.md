## Longest Consecutive Sequence in an Array (c++)

Given an unsorted array of integers nums, return the length of the longest consecutive elements sequence.

You must write an algorithm that runs in O(n) time.
## Example
Input: nums = [100,4,200,1,3,2]

Output: 4

Explanation: The longest consecutive elements sequence is [1, 2, 3, 4]. Therefore its length is 4.

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    int longestConsecutive(vector<int>& nums) 
    {
        int n=nums.size();
        int longest=1;
        unordered_set<int> st;
        
        if(n==0) return 0;
        for (int i=0;i<n;i++)
        {
            st.insert(nums[i]);
        }
        for(auto it :st)
        {
            if(st.find(it -1)==st.end())
            {
                int x=it;
                int cnt=1;
                while(st.find(x+1)!=st.end())
                {
                    x=x+1;
                    cnt=cnt+1;
                }
                longest=max(longest,cnt);
            }       
        }
        return longest;   
    }
};
```
## Complexity
- Time complexity : O(N) + O(2*N) ~ O(3*N)

- Space complexity : O(N)

## OUTPUT
Output: 4
