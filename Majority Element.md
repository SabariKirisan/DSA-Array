## Find the Majority Element that occurs more than N/2 times (c++)

GGiven an array nums of size n, return the majority element.

The majority element is the element that appears more than ⌊n / 2⌋ times. You may assume that the majority element always exists in the array.
## Example
Input: nums = [2,2,1,1,1,2,2]

Output: 2

## PROGRAM:(Main.cpp)
```
class Solution {
class Solution {
public:
    int majorityElement(vector<int>& nums) {

        int n=nums.size();
        int majority=n/2;
        int ele=0;
        int cnt=0;
        for (int i=0;i<n;i++)
        {
            if(cnt==0)
            {
                ele=nums[i];
                cnt++;
            }
            else if(ele != nums[i]) cnt--;
            else cnt++;
        }
        int cnt1=0;
        for(int i=0;i<n;i++)
        {
            if(ele==nums[i]) cnt1++;
        }
        if(cnt1 > majority ) return ele;

        return -1;

    }
};
```
## Complexity
- Time complexity : O(N + N)

- Space complexity : O(1)

## OUTPUT
Output: 2
