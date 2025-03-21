## Maximum Score from Subarray Minimums (c++)

Given an array arr[], with 0-based indexing, select any two indexes, i and j such that i < j. From the subarray arr[i...j], select the smallest and second smallest numbers and add them, you will get the score for that subarray. Return the maximum possible score across all the subarrays of array arr[].
## Example
Input : arr[] = [4, 3, 1, 5, 6]

Output : 11

Explanation : Subarrays with smallest and second smallest are:- [4, 3] smallest = 3,second smallest = 4
[4, 3, 1] smallest = 1, second smallest = 3
[4, 3, 1, 5] smallest = 1, second smallest = 3
[4, 3, 1, 5, 6] smallest = 1, second smallest = 3
[3, 1] smallest = 1, second smallest = 3
[3, 1, 5] smallest = 1, second smallest = 3
[3, 1, 5, 6] smallest = 1, second smallest = 3
[1, 5] smallest = 1, second smallest = 5
[1, 5, 6] smallest = 1, second smallest = 5
[5, 6] smallest = 5, second smallest = 6
Maximum sum among all above choices is, 5 + 6 = 11.

## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    int pairWithMaxSum(vector<int> &arr) {
        
        int n=arr.size();
        long long int maxx=-1;
        for(int i=0;i<n-1;i++)
        {
            long long int sum=0;
            for(int j=i;j<i+2;j++)
            {
                sum=sum+arr[j];
            }
            maxx=max(maxx,sum);
        }
        return maxx;
    }
};
```
## Complexity
- Time complexity : O(N)

- Space complexity : O(1)

## OUTPUT
Output: 11
