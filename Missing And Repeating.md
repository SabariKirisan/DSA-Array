## Missing And Repeating (c++)

Given an unsorted array arr of positive integers. One number a from the set [1, 2,....,n] is missing and one number b occurs twice in the array. Find numbers a and b.

Note: The test cases are generated such that there always exists one missing and one repeating number within the range [1,n].
## Example
Input: arr[] = [1, 3, 3] 

Output: [3, 2]

Explanation: Repeating number is 3 and smallest positive missing number is 2.
## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    vector<int> findTwoElement(vector<int>& arr) {
       long long n=arr.size();
       long long sn=(n*(n+1))/2;
       long long s2n=(n*(n+1)*(2*n+1))/6;
       long long s=0,s2=0;
       for(int i=0;i<n;i++)
       {
           s+=arr[i];
           s2+=(long long)arr[i]*(long long) arr[i];
       }
       long long val1=s-sn;
       long long val2=s2-s2n;
       val2=val2/val1;
       long long x=(val1+val2)/2;
       long long y=x-val1;
       return{(int)x,(int)y};
    }
};
```
## Complexity
- Time complexity : O(n)

- Space complexity : O(1)

## OUTPUT
Output: [3, 2]
