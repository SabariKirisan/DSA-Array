## Largest Element in Array (c++)
Given an array arr[]. The task is to find the largest element and return it.

Input: arr[] = [1, 8, 7, 56, 90]

Output: 90

Explanation: The largest element of the given array is 90.

## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    int largest(vector<int> &arr) {
        int n=arr.size();
        int max=arr[0];
        for (int i=0;i<n;i++)
        {
            if(max<arr[i])
            {
                max=arr[i];
            }
        }
        return max;
    }
};
```

## Complexity
- Time complexity : O(n)

- Space complexity : O(1)

## OUTPUT
Output: 90
