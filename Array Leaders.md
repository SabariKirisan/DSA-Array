## Array Leaders (c++)

You are given an array arr of positive integers. Your task is to find all the leaders in the array. An element is considered a leader if it is greater than or equal to all elements to its right. The rightmost element is always a leader.
## Example
Input: arr = [16, 17, 4, 3, 5, 2]

Output: [17, 5, 2]

Explanation: Note that there is nothing greater on the right side of 17, 5 and, 2.

## PROGRAM:(Main.cpp)
```
 class Solution {
public:
    vector<int> leaders(vector<int>& arr) {
          int n=arr.size();
          int maxi=INT_MIN;
          vector<int>ans;
          for(int i=n-1;i>=0;i--)
          {
             if(arr[i]>=maxi)
             {
                 ans.push_back(arr[i]);
             }
              maxi=max(maxi,arr[i]);
          }
          reverse(ans.begin(),ans.end());
          return ans;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(N)

## OUTPUT
Output: [17, 5, 2]
