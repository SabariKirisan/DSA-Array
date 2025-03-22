## Count inversions in an array (c++)

Given an array of integers arr[]. Find the Inversion Count in the array.
Two elements arr[i] and arr[j] form an inversion if arr[i] > arr[j] and i < j.

Inversion Count: For an array, inversion count indicates how far (or close) the array is from being sorted. If the array is already sorted then the inversion count is 0.
If an array is sorted in the reverse order then the inversion count is the maximum. 
## Example
Input: arr[] = [2, 4, 1, 3, 5]

Output: 3

Explanation: The sequence 2, 4, 1, 3, 5 has three inversions (2, 1), (4, 1), (4, 3).
## PROGRAM:(Main.cpp)
```
class Solution {
  public:
    int merge(vector<int> &arr, int low, int mid, int high) 
    {
    vector<int> temp;    // temporary array
    int left = low;      // starting index of left half of arr
    int right = mid + 1; // starting index of right half of arr

    //Modification 1: cnt variable to count the pairs:
    int cnt = 0;

    //storing elements in the temporary array in a sorted manner//

    while (left <= mid && right <= high) 
    {
        if (arr[left] <= arr[right]) 
        {
            temp.push_back(arr[left]);
            left++;
        }
        else 
        {
            temp.push_back(arr[right]);
            cnt += (mid - left + 1); //Modification 2
            right++;
        }
    }

    // if elements on the left half are still left 

    while (left <= mid) 
    {
        temp.push_back(arr[left]);
        left++;
    }

    //  if elements on the right half are still left 
    while (right <= high) 
    {
        temp.push_back(arr[right]);
        right++;
    }

    // transfering all elements from temporary to arr 
    for (int i = low; i <= high; i++) 
    {
        arr[i] = temp[i - low];
    }

    return cnt; // Modification 3
}

    int mergeSort(vector<int> &arr, int low, int high) 
    {
    int cnt = 0;
    if (low >= high) return cnt;
    int mid = (low + high) / 2 ;
    cnt += mergeSort(arr, low, mid);  // left half
    cnt += mergeSort(arr, mid + 1, high); // right half
    cnt += merge(arr, low, mid, high);  // merging sorted halves
    return cnt;
    }

    int inversionCount(vector<int> &arr) 
    {
        int n=arr.size();
        return mergeSort(arr, 0, n - 1);
    }
};
```
## Complexity
- Time complexity :  O(n log n)

- Space complexity : O(n)

## OUTPUT
Output: 3
