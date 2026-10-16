## 01. Rotate Array

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/rotate-array-by-n-elements-1587115621/1)

### Problem Description

**Task:** Given an array arr[]. Rotate the array to the left (counter-clockwise direction) by d steps, where d is a positive integer. Do the mentioned change in the array in place.Note: Consider the array as circular.Examples :Input: arr[] = [1, 2, 3, 4, 5], d = 2

#### Examples

##### Example 1

- **Output:**
```text
[3, 9, 1, 7]
```
- **Explanation:** when we rotate 9 times, we'll get [3, 9, 1, 7] as resultant array.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (3)

#### Solution 1 (Python)

- **Submitted:** 2026-10-16 12:35:21
- **Status:** Correct
- **Marks:** 0

```python
class Solution:
    def rotateArr(self, arr, d):
        d%=len(arr)
        for i in range(d//2):
            arr[i],arr[d-1-i]=arr[d-1-i],arr[i]
        for i in range(d,d+(len(arr)-d)//2):
            arr[i],arr[len(arr)+d-1-i]=arr[len(arr)+d-1-i],arr[i]
        for i in range(len(arr)//2):
            arr[i],arr[len(arr)-1-i]=arr[len(arr)-1-i],arr[i]
```

#### Solution 2 (Python)

- **Submitted:** 2026-10-16 11:50:10
- **Status:** Correct
- **Marks:** 0

```python
class Solution {
    public void rotateArr(int[] arr, int d) {
        d%=arr.length;
        for(int i=0;i<d/2;i++){
            arr[i]=arr[i]^arr[d-i-1];
            arr[d-i-1]=arr[i]^arr[d-i-1];
            arr[i]=arr[i]^arr[d-i-1];
        }
        for(int i=d;i<d+(arr.length-d)/2;i++){
            arr[i]=arr[i]^arr[arr.length +d-1-i];
            arr[arr.length+d-1-i]=arr[i]^arr[arr.length+d-1-i];
            arr[i]=arr[i]^arr[arr.length+d-1-i];
        }
        for(int i=0;i<arr.length/2;i++){
            arr[i]=arr[i]^arr[arr.length-1-i];
            arr[arr.length-1-i]=arr[i]^arr[arr.length-1-i];
            arr[i]=arr[i]^arr[arr.length-1-i];
        }
    }
    
};
```

#### Solution 3 (Python)

- **Submitted:** 2026-10-16 11:30:23
- **Status:** Correct
- **Marks:** 4

```python
class Solution {
  public:
    void rotateArr(vector<int>& arr, int d) {
        reverse(arr.begin(),arr.begin()+d%arr.size());
        reverse(arr.begin()+d%arr.size(),arr.end());
        reverse(arr.begin(),arr.end());
    }
};
```

*Generated on: 10/16/2026, 12:36:56 PM*