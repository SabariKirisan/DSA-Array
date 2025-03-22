## Program to generate Pascal's Triangle (c++)

Given an integer numRows, return the first numRows of Pascal's triangle.

In Pascal's triangle, each number is the sum of the two numbers directly above it as shown:

![image](https://github.com/user-attachments/assets/0ba677b5-5572-4e6c-b7d7-b232a0a968ac)



## Example
Input: numRows = 5

Output: [[1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1]]

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    vector<int> pascal(int row)
    {
        vector<int> ansrow;
        long long ans=1;
        ansrow.push_back(1);
        for(int col=1;col<row;col++)
        {
            ans=ans*(row-col);
            ans=ans/(col);
            ansrow.push_back(ans);
        }
        return ansrow;    
    }
    vector<vector<int>> generate(int numRows) 
    {
        vector<vector<int>> finalans;
       
        for(int i=1;i<=numRows;i++)
        {
            finalans.push_back(pascal(i));
        }
        return finalans;    
    }
};
```
## Complexity
- Time complexity : O(N2)

- Space complexity : O(1)

## OUTPUT
Output: [[1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1]]
