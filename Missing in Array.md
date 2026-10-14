## 01. Missing in Array

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/missing-number-in-array1416/1)

### Problem Description

**Task:** You are given an array arr[] of size n - 1 that contains distinct integers in the range from 1 to n (inclusive). This array represents a permutation of the integers from 1 to n with one element missing. Your task is to identify and return the missing element.Examples:Input: arr[] = [1, 2, 3, 5]

#### Examples

##### Example 1

- **Output:**
```text
2
```
- **Explanation:** Only 1 is present so the missing element is 2.Constraints:1 ≤ arr.size() ≤ 10⁶¹ ≤ arr[i] ≤ arr.size() + 1

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (3)

#### Solution 1 (Python)

- **Submitted:** 2026-10-14 10:59:52
- **Status:** Correct
- **Marks:** 0

```python
class Solution:
    def missingNum(self, arr):
        n=len(arr)
        return (n+1)*(n+2)//2 - sum(arr)
```

#### Solution 2 (Python)

- **Submitted:** 2026-10-14 10:58:11
- **Status:** Correct
- **Marks:** 0

```python
import java.util.Collections;
class Solution {
    int missingNum(int arr[]) {
        int n = arr.length;
        return (int)(1l*(n+1)*(n+2)/2 - Arrays.stream(arr).asLongStream().sum());//accumulate returns the total sum and 0ll is taken as long long because of overflow risks
    }
}
```

#### Solution 3 (Python)

- **Submitted:** 2026-10-14 10:54:23
- **Status:** Correct
- **Marks:** 2

```python
class Solution {
  public:
    int missingNum(vector<int>& arr) {
        int n = arr.size();
        return (1ll*(n+1)*(n+2)/2 - accumulate(arr.begin(),arr.end(),0ll));//accumulate returns the total sum and 0ll is taken as long long because of overflow risks
    }
};
```

*Generated on: 10/14/2026, 11:00:18 AM*