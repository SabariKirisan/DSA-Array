## Second Largest Element in Array (c++)
Given an array of positive integers arr[], return the second largest element from the array. If the second largest element doesn't exist then return -1.

Note: The second largest element should not be equal to the largest element.

Input: arr[] = [12, 35, 1, 10, 34, 1]

Output: 34

Explanation: The largest element of the array is 35 and the second largest element is 34.

## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    int getSecondLargest(vector<int> &arr) {
        int n=arr.size();
        int largest=INT_MIN;
        int s_largest=INT_MIN;
        if(n<2) return -1;
            for(int i=0;i<n;i++)
            {
                if(arr[i]>largest)
                {
                    s_largest=largest;
                    largest=arr[i];
                    
                }
                else if(arr[i]>s_largest && arr[i]!=largest)
                {
                    s_largest=arr[i];
                }
            }
        return (s_largest == INT_MIN) ? -1 : s_largest;
    }
};
```
## Complexity
- Time complexity : O(n)

- Space complexity : O(1)

## OUTPUT
Output: 34
