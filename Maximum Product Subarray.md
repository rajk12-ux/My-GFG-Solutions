## 01. Maximum Product Subarray

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/maximum-product-subarray3604/1)

### Problem Description

**Task:** Given an array arr[] that contains positive and negative integers (may contain 0 as well). Find the maximum product that we can get in a subarray of arr[].Note: It is guaranteed that the answer fits in a 32-bit integer.ExamplesInput: arr[] = [-2, 6, -3, -10, 0, 2]

#### Examples

##### Example 1

- **Output:**
```text
30
```
- **Explanation:** The subarray with maximum product is [-3, -10] with product = (-3) * (-10) = 30.Input: arr[] = [2, 3, 4] Output: 24 Explanation: For an array with all positive elements, the result is product of all elements.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (3)

#### Solution 1 (Python)

- **Submitted:** 2026-10-20 11:37:16
- **Status:** Correct
- **Marks:** 0

```python
class Solution:
    def maxProduct(self, arr):
        curr_max=arr[0]
        curr_min=arr[0]
        max_prod=arr[0]
        for i in range(1,len(arr)):
            temp_max=max(arr[i],arr[i]*curr_min,arr[i]*curr_max)
            temp_min=min(arr[i],arr[i]*curr_min,arr[i]*curr_max)
            curr_max=temp_max
            curr_min=temp_min
            max_prod=max(max_prod,curr_max)
        return max_prod
```

#### Solution 2 (Python)

- **Submitted:** 2026-10-20 11:35:42
- **Status:** Correct
- **Marks:** 0

```python
class Solution {
    int maxProduct(int[] arr) {
        int curr_maxx=arr[0];
        int curr_minn=arr[0];
        int maxx_prod=arr[0];
        for(int i=1;i<arr.length;i++){
            int temp_maxx=Math.max(arr[i],Math.max(arr[i]*curr_minn,arr[i]*curr_maxx));
            int temp_minn=Math.min(arr[i],Math.min(arr[i]*curr_minn,arr[i]*curr_maxx));
            curr_maxx=temp_maxx;
            curr_minn=temp_minn;
            maxx_prod=Math.max(maxx_prod,curr_maxx);
        }
        return maxx_prod;
    }
}
```

#### Solution 3 (Python)

- **Submitted:** 2026-10-20 11:31:29
- **Status:** Correct
- **Marks:** 4

```python
class Solution {
  public:
    int maxProduct(vector<int> &arr) {
        int curr_max=arr[0];
        int curr_min=arr[0];
        int max_prod=arr[0];
        for(int i=1;i<arr.size();i++){
            int temp_max=max({arr[i],arr[i]*curr_min,arr[i]*curr_max});
            int temp_min=min({arr[i],arr[i]*curr_min,arr[i]*curr_max});
            curr_max=temp_max;
            curr_min=temp_min;
            max_prod=max(max_prod,curr_max);
        }
        return max_prod;
    }
};
```

*Generated on: 10/20/2026, 11:37:43 AM*