## Intersection of two sorted arrays (c++)
Given two sorted arrays arr1[] and arr2[]. Your task is to return the intersection of both arrays.

Intersection of two arrays is said to be elements that are common in both arrays. The intersection should not count duplicate elements.

Note: If there is no intersection then return an empty array.

Input: arr1[] = [1, 2, 2, 3, 4], arr2[] = [2, 2, 4, 6, 7, 8]

Output: [2, 4]

Explanation: 2 and 4 are the only common elements.

## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    // Function to return a list containing the intersection of two arrays.
    vector<int> intersection(vector<int> &arr1, vector<int> &arr2) {
        int n=arr1.size();
        int m=arr2.size();
        int i=0;
        int j=0;
        
        vector<int> ans;
        
        while(i<n && j<m)
        {
            if(i>0 && arr1[i]==arr1[i-1])
            {
                i++;
                continue;
            }
            if(j>0 && arr2[j]==arr2[j-1])
            {
                j++;
                continue;
            }
            if(arr1[i]<arr2[j])
            {
                i++;
            }
            else if(arr1[i]>arr2[j])
            {
                j++;
            }
            else
            {
                ans.push_back(arr1[i]);
                i++;
                j++;
            }
        }
        return ans;
    }
};
```

## Complexity
- Time complexity : O(n + m)

- Space complexity : 

    O(1) (if we ignore output storage)

    O(min(n,m) (if we include output storage)

## OUTPUT
Output:  [2, 4]
