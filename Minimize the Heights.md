## 01. Minimize the Heights

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/minimize-the-heights3351/1)

### Problem Description

**Task:** Given an array arr[] representing the heights of n towers and a positive integer k. For each tower, perform exactly one of the following operations exactly once:Increase its height by k, orDecrease its height by k.After performing the operation on every tower, the height of any tower must not become negative.Return the minimum possible difference between the heights of the tallest and the shortest towers after modifying all the towers.Examples :Input: k = 2, arr[] = [1, 5, 8, 10]

#### Examples

##### Example 1

- **Output:**
```text
5
```
- **Explanation:** The array can be modified as [1+k, 5-k, 8-k, 10-k] = [3, 3, 6, 8]. The difference between the largest and the smallest is 8-3 = 5.

##### Example 2

- **Input:**
```text
k = 3, arr[] = [3, 9, 12, 16, 20]
```
- **Output:**
```text
11
```
- **Explanation:** The array can be modified as [3+k, 9+k, 12-k, 16-k, 20-k] = [6, 12, 9, 13, 17]. The difference between the largest and the smallest is 17-6 = 11.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n log n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (3)

#### Solution 1 (Python)

- **Submitted:** 2026-10-14 19:13:46
- **Status:** Correct
- **Marks:** 0

```python
class Solution:
    def getMinDiff(self, arr, k):
        arr.sort();
        curH=arr[len(arr)-1]-arr[0];
        for i in range(1,len(arr)):
            if(arr[i]<k):
                continue
            minH=min(arr[0]+k,arr[i]-k);
            maxH=max(arr[len(arr)-1]-k,arr[i-1]+k);
            curH=min(curH,maxH-minH)
        return curH
```

#### Solution 2 (Python)

- **Submitted:** 2026-10-14 19:09:21
- **Status:** Correct
- **Marks:** 0

```python
class Solution {
    public int getMinDiff(int[] arr, int k) {
        Arrays.sort(arr);
        int curH=arr[arr.length-1]-arr[0];
        for(int i=1;i<arr.length;i++){
            if(arr[i]<k)continue;
            int minH=Math.min(arr[0]+k,arr[i]-k);
            int maxH=Math.max(arr[arr.length-1]-k,arr[i-1]+k);
            curH=Math.min(curH,maxH-minH);
        }
        return curH;
        
    }
}
```

#### Solution 3 (Python)

- **Submitted:** 2026-10-14 19:04:51
- **Status:** Correct
- **Marks:** 4

```python
class Solution {
  public:
    int getMinDiff(vector<int> &arr, int k) {
        sort(arr.begin(),arr.end());
        int curH=arr[arr.size()-1]-arr[0];
        for(int i=0;i<arr.size();i++){
            if(arr[i]<k)continue;
            int minH=min(arr[0]+k,arr[i]-k);
            int maxH=max(arr[arr.size()-1]-k,arr[i-1]+k);
            curH=min(curH,maxH-minH);
        }
        return curH;
    }
};
```

*Generated on: 10/14/2026, 7:14:08 PM*