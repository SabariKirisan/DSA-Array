## nion of 2 Sorted with Duplicates (c++)
Given two sorted arrays a[] and b[], where each array may contain duplicate elements , the task is to return the elements in the union of the two arrays in sorted order.

Union of two arrays can be defined as the set containing distinct common elements that are present in either of the arrays.

nput: a[] = [1, 2, 3, 4, 5], b[] = [1, 2, 3, 6, 7]

Output: 1 2 3 4 5 6 7

Explanation: Distinct elements including both the arrays are: 1 2 3 4 5 6 7.

## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    vector<int> findUnion(vector<int> &a, vector<int> &b) {
        int n1=a.size();
        int n2=b.size();
        int i=0;
        int j=0;
        vector<int> arr;
        
        while(i<n1 && j<n2)
        {
         if(a[i]<b[j])
         {
            if(arr.size()==0 || arr.back()!=a[i])
            {
                arr.push_back(a[i]);
            }
            i++;
         }
        else if(a[i]>b[j])
            {
                if(arr.size()==0 || arr.back()!=b[j])
                {
                    arr.push_back(b[j]);
                }
                j++;
            }
        else
            {
               if(arr.size()==0 || arr.back()!=a[i])
               {
                   arr.push_back(a[i]);
               }
                i++;
                j++;
            }
        }
        while(i<n1)
        {
            if(arr.back()!=a[i])
            {
                arr.push_back(a[i]);
            }
            i++;
        }
        while(j<n2)
        {
             if(arr.back()!=b[j])
                {
                    arr.push_back(b[j]);
                }
                j++;
        }
        return arr;
    }
};
```

## Complexity
- Time complexity : O(n1 + n2) (since we traverse both arrays once).

- Space complexity : O(n1 + n2) (for storing the result).

## OUTPUT
Output: 1 2 3 4 5 6 7
