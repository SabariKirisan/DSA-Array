## Set Matrix Zero (c++)

GGiven an m x n integer matrix matrix, if an element is 0, set its entire row and column to 0's.

You must do it in place.
## Example
![image](https://github.com/user-attachments/assets/0e24b524-cf34-4748-9723-0323dc0e1267)

Input: matrix = [[1,1,1],[1,0,1],[1,1,1]]

Output: [[1,0,1],[0,0,0],[1,0,1]]

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    void setZeroes(vector<vector<int>>& matrix) {
        int n=matrix.size();
        int m=matrix[0].size();
        int colo=1;

        for(int i=0;i<n;i++)
        {
            for(int j=0;j<m;j++)
            {
                if(matrix[i][j]==0)
                {
                    matrix[i][0]=0;

                    if(j!=0) matrix[0][j]=0;
                    else colo=0;
                }
            }
        }
        for(int i=1;i<n;i++)
        {
            for(int j=1;j<m;j++)
            {
                if(matrix[i][j]!=0)
                {
                    if(matrix[0][j]==0 || matrix[i][0]==0)
                    {
                        matrix[i][j]=0;
                    }
                }
            }
        }
        if(matrix[0][0]==0)
        {
            for(int j=0;j<m;j++)
            {
                matrix[0][j]=0;
            }
        }
        if(colo==0)
        {
            for(int i=0;i<n;i++)
            {
                matrix[i][0]=0;
            }
        }
        
    }
};
```
## Complexity
- Time complexity : O(N * M)
- Space complexity : O(1)

## OUTPUT
Output: [[1,0,1],[0,0,0],[1,0,1]]
