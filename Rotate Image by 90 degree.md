## Rotate Image by 90 degree (c++)

You are given an n x n 2D matrix representing an image, rotate the image by 90 degrees (clockwise).

You have to rotate the image in-place, which means you have to modify the input 2D matrix directly. DO NOT allocate another 2D matrix and do the rotation.
## Example
![image](https://github.com/user-attachments/assets/fc8992e6-4618-4e64-91de-2370ef07a56d)

Input: matrix = [[1,2,3],[4,5,6],[7,8,9]]

Output: [[7,4,1],[8,5,2],[9,6,3]]

## PROGRAM:(Main.cpp)
```
class Solution {
public:
    void rotate(vector<vector<int>>& matrix) 
    {
        int n=matrix.size();
        for(int i=0;i<n-1;i++)
        {
            for(int j=i+1;j<n;j++)
            {
                swap(matrix[i][j],matrix[j][i]);
            }
        }
        for(int i=0;i<n;i++)
        {
            reverse(matrix[i].begin(),matrix[i].end());
        }
    }
};
```
## Complexity
- Time complexity : O(N*N) + O(N*N).One O(N*N) is for transposing the matrix and the other is for reversing the matrix.

- Space complexity : O(1)

## OUTPUT
Output: [[7,4,1],[8,5,2],[9,6,3]]
