## 01. Kadane's Algorithm

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/kadanes-algorithm-1587115620/1)

### Problem Description

**Task:** You are given an integer array arr[]. You need to find the maximum sum of a subarray (containing at least one element) in the array arr[].Examples:Input: arr[] = [2, 3, -8, 7, -1, 2, 3]

#### Examples

##### Example 1

- **Output:**
```text
11
```
- **Explanation:** The subarray [7, -1, 2, 3] has the largest sum 11.

##### Example 2

- **Input:**
```text
arr[] = [-2, -4]
```
- **Output:**
```text
25
```
- **Explanation:** The subarray [5, 4, 1, 7, 8] has the largest sum 25.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (5)

#### Solution 1 (Python)

- **Submitted:** 2026-10-14 10:44:31
- **Status:** Correct
- **Marks:** 0

```python
class Solution:
    def maxSubarraySum(self, arr):
        curr=0#current sum
        maxx=0#max sum till now
        for i in range(len(arr)):
            curr += arr[i]
            if(curr<0):
                curr=0
            maxx=max(curr,maxx)
        if (maxx==0):
            return max(arr)#the function returns iterator to maximum element hence * is used to dereference it
        return maxx
```

#### Solution 2 (Python)

- **Submitted:** 2026-10-14 10:10:20
- **Status:** Correct
- **Marks:** 0

```python
import java.util.Arrays;
class Solution {
    int maxSubarraySum(int[] arr) {
        int l=0,r=0;
        int curr=0;//current sum
        int maxx=0;//max sum till now
        for(int i=0;i<arr.length;i++){
            curr += arr[i];
            if(curr<0)curr=0;
            maxx=Math.max(curr,maxx);
        }
        if (maxx == 0) return Arrays.stream(arr).max().getAsInt();//find the maximum element of array
        return maxx;
    }
}
```

#### Solution 3 (Python)

- **Submitted:** 2026-10-14 10:09:42
- **Status:** Correct
- **Marks:** 0

```python
import java.util.Arrays;
class Solution {
    int maxSubarraySum(int[] arr) {
        int l=0,r=0;
        int curr=0;//current sum
        int maxx=0;//max sum till now
        for(int i=0;i<arr.length;i++){
            curr += arr[i];
            if(curr<0)curr=0;
            maxx=Math.max(curr,maxx);
        }
        if (maxx == 0) return Arrays.stream(arr).max().getAsInt();
        return maxx;
    }
}
```

#### Solution 4 (Python)

- **Submitted:** 2026-10-14 10:07:18
- **Status:** Correct
- **Marks:** 0

```python
class Solution {
  public:
    int maxSubarraySum(vector<int> &arr) {
        int l=0,r=0;
        int curr=0;//current sum
        int maxx=0;//max sum till now
        for(int i=0;i<arr.size();i++){
            curr += arr[i];
            if(curr<0)curr=0;
            maxx=max(curr,maxx);
        }
        if (maxx==0)return *max_element(arr.begin(), arr.end());//the function returns iterator to maximum element hence * is used to dereference it
        return maxx;
    }
};
```

#### Solution 5 (Python)

- **Submitted:** 2026-10-12 15:35:53
- **Status:** Correct
- **Marks:** 4

```python
class Solution {
  public:
    int maxSubarraySum(vector<int> &arr) {
        int l=0,r=0;
        int curr=0;//current sum
        int maxx=0;//max sum till now
        for(int i=0;i<arr.size();i++){
            curr += arr[i];
            if(curr<0)curr=0;
            maxx=max(curr,maxx);
        }
        if (maxx==0)return *max_element(arr.begin(), arr.end());//the function returns iterator to maximum element hence * is used to dereference it
        return maxx;
    }
};
```

*Generated on: 10/14/2026, 10:44:57 AM*