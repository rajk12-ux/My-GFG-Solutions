## 01. Max Circular Subarray Sum

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/max-circular-subarray-sum-1587115620/1)

### Problem Description

**Task:** You are given a circular array arr[] of integers, find the maximum possible sum of a non-empty subarray. In a circular array, the subarray can start at the end and wrap around to the beginning. Return the maximum non-empty subarray sum, considering both non-wrapping and wrapping cases.Examples:Input: arr[] = [8, -8, 9, -9, 10, -11, 12]

#### Examples

##### Example 1

- **Output:**
```text
23
```
- **Explanation:** The circular subarray [3, 4, 5] gives the maximum sum of 12.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (3)

#### Solution 1 (Python)

- **Submitted:** 2026-10-26 13:29:31
- **Status:** Correct
- **Marks:** 0

```python
class Solution:
    def minSubArrSum(int, arr):
        curr=arr[0]
        minn=arr[0]
        for i in range(1,len(arr)):
            curr=min(arr[i],curr+arr[i])
            minn=min(minn,curr)
        return minn
    
    def maxSubArrSum(int, arr):
        curr=arr[0]
        maxx=arr[0]
        for i in range(1,len(arr)):
            curr=max(arr[i],curr+arr[i])
            maxx=max(maxx,curr)
        return maxx
    
    def maxCircularSum(self, arr):
        minSubArr=self.minSubArrSum(arr)
        maxSubArr=self.maxSubArrSum(arr)
        summ=sum(arr)
        if maxSubArr<0:
            return maxSubArr
        return max(summ-minSubArr,maxSubArr)
```

#### Solution 2 (Python)

- **Submitted:** 2026-10-26 13:20:44
- **Status:** Correct
- **Marks:** 0

```python
class Solution {
    int minSubArrSum(int arr[]){
        int curr=arr[0],minn=arr[0];
        for(int i=1;i<arr.length;i++){
            curr=Math.min(arr[i],curr+arr[i]);
            minn=Math.min(minn,curr);
        }
        return minn;
    }
    int maxSubArrSum(int arr[]){
        int curr=arr[0],maxx=arr[0];
        for(int i=1;i<arr.length;i++){
            curr=Math.max(arr[i],curr+arr[i]);
            maxx=Math.max(maxx,curr);
        }
        return maxx;
    }
    public int maxCircularSum(int arr[]) {
        int minSubArr=minSubArrSum(arr);
        int maxSubArr=maxSubArrSum(arr);
        int summ=Arrays.stream(arr).sum();
        if(maxSubArr<0)return maxSubArr;
        return Math.max(summ-minSubArr,maxSubArr);
    }
}
```

#### Solution 3 (Python)

- **Submitted:** 2026-10-26 13:16:20
- **Status:** Correct
- **Marks:** 8

```python
class Solution {
  public:
    int minSubArrSum(vector<int> arr){
        int curr=arr[0],minn=arr[0];
        for(int i=1;i<arr.size();i++){
            curr=min(arr[i],curr+arr[i]);
            minn=min(minn,curr);
        }
        return minn;
    }
    int maxSubArrSum(vector<int> arr){
        int curr=arr[0],maxx=arr[0];
        for(int i=1;i<arr.size();i++){
            curr=max(arr[i],curr+arr[i]);
            maxx=max(maxx,curr);
        }
        return maxx;
    }
    int maxCircularSum(vector<int> &arr) {
        int minSubArr=minSubArrSum(arr);
        int maxSubArr=maxSubArrSum(arr);
        int summ=accumulate(arr.begin(),arr.end(),0);
        if(maxSubArr<0)return maxSubArr;
        return max(summ-minSubArr,maxSubArr);
    }
};
```

*Generated on: 10/26/2026, 1:30:06 PM*