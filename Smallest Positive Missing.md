## 01. Smallest Positive Missing

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/smallest-positive-missing-number-1587115621/1)

### Problem Description

**Task:** You are given an integer array arr[]. Your task is to find the smallest positive number missing from the array.Note: Positive number starts from 1. The array can have negative integers too.Examples:Input: arr[] = [2, -3, 4, 1, 1, 7]

#### Examples

##### Example 1

- **Output:**
```text
3
```
- **Explanation:** Smallest positive missing number is 3.

##### Example 2

- **Input:**
```text
arr[] = [5, 3, 2, 5, 1]
```
- **Output:**
```text
1
```
- **Explanation:** Smallest positive missing number is 1.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (3)

#### Solution 1 (Python)

- **Submitted:** 2026-10-28 15:40:29
- **Status:** Correct
- **Marks:** 0

```python
class Solution:
    def missingNumber(self, arr):
        nums=set(arr)
        n=1
        while True:
            if n not in nums:
               return n
            n += 1
        return 0
```

#### Solution 2 (Python)

- **Submitted:** 2026-10-28 15:35:56
- **Status:** Correct
- **Marks:** 0

```python
import java.util.*;
import java.util.stream.*;
class Solution {
    public int missingNumber(int[] arr) {
        HashSet<Integer> nums = Arrays.stream(arr).boxed().collect(Collectors.toCollection(HashSet::new));
        int n=1;
        while(true){
            if (!nums.contains(n)) {
                return n;
                }
            ++n;
        }
    }
}
```

#### Solution 3 (Python)

- **Submitted:** 2026-10-28 15:22:09
- **Status:** Correct
- **Marks:** 4

```python
class Solution {
  public:
    int missingNumber(vector<int> &arr) {
        unordered_set<int> nums(arr.begin(),arr.end());
        int n=1;
        while(n){
            if(nums.find(n)==nums.end())return n;
            ++n;
        }
        return 0;
    }
};
```

*Generated on: 10/28/2026, 3:41:28 PM*