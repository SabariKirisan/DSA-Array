## Valid Anagram (c++)

Given two strings s and t, return true if t is an anagram of s, and false otherwise.

## Example
Input: s = "anagram", t = "nagaram"

Output: true

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    bool isAnagram(string s, string t) 
    {
        if(s.size()!=t.size())
        {
            return false;
        }
        unordered_map<char,int> counts;
        unordered_map<char,int> countt;
        for(int i=0;i<s.size();i++)
        {
            counts[s[i]]++;
            countt[t[i]]++;
        }
        return counts==countt;
    }
};
```
## Complexity
- Time complexity : O(s+t)

- Space complexity : O(1)
