## Longest Common Prefix (c++)

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

## Example
Input: strs = ["flower","flow","flight"]

Output: "fl"

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) 
    {
        if(strs.empty()) return "";
        if(strs.size()==1) return strs[0];
        sort(strs.begin(),strs.end());
        string first=strs[0];
        string last=strs.back();
        int i=0;
        while(i<first.length() && i<last.length() && first[i]==last[i])
        {
            i++;
        }
        return first.substr(0,i);
    }
};
```
## Complexity
- Time complexity : O(n∗mlogm)

- Space complexity : O(1)
