## Find the elements that appears more than N/3 times in the array  (c++)

Given an integer array of size n, find all elements that appear more than ⌊ n/3 ⌋ times.
## Example
Input: nums = [3,2,3]

Output: [3]
## PROGRAM:(Main.cpp)
```
class Solution {
public:
    vector<int> majorityElement(vector<int>& nums) {
        int n=nums.size();
        int cnt1=0,cnt2=0;
        int ele1=0,ele2=0;
        for(int i=0;i<n;i++)
        {
            if(cnt1==0 && nums[i]!=ele2)
            {
                ele1=nums[i];
                cnt1=1;
            }
            else if(cnt2==0 && nums[i]!=ele1)
            {
                ele2=nums[i];
                cnt2=1;
            }
            else if(ele1 == nums[i]) cnt1++;
            else if(ele2 == nums[i]) cnt2++;

            else
            {
                cnt1--;
                cnt2--;
            }
        }

        vector<int> ls;
        cnt1 = 0, cnt2 = 0;
        for(int i=0;i<n;i++)
        {
            if(ele1==nums[i])  cnt1++;
            if(ele2==nums[i])  cnt2++;
        }
        int mini = int(n/3)+1;

        if(cnt1>=mini) ls.push_back(ele1);
        if(cnt2>=mini && ele1!=ele2) ls.push_back(ele2);

        return ls;
    }
};
```
## Complexity
- Time complexity : O(N) + O(N)

- Space complexity : O(1)

## OUTPUT
Output: [3]
