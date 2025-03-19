## First and Second Smallests (c++)

Given an array, arr of integers, your task is to return the smallest and second smallest element in the array. If the smallest and second smallest do not exist, return -1.

Input: arr[] = [2, 4, 3, 5, 6]

Output: 2 3 

Explanation: 2 and 3 are respectively the smallest and second smallest elements in the array.

## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    vector<int> minAnd2ndMin(vector<int> &arr) {
        int n=arr.size();
        int small=INT_MAX;
        int s_small=INT_MAX;
        
        if(n<2) return {-1,-1};
        
        for(int i=0;i<n;i++)
        {
            if(arr[i]<small)
            {
                s_small=small;
                small=arr[i];
            }
            else if (arr[i]<s_small && arr[i]!=small)
            {
                s_small=arr[i];
            }
        }
        if(s_small==INT_MAX) return {-1,-1};
        return {small,s_small};
    }
};
```

## OUTPUT
Output: 2 3
