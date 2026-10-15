## 01. Move All Zeroes to End

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/move-all-zeroes-to-end-of-array0751/1)

### Problem Description

**Task:** Given an array arr[] of non-negative integers, move all the zeros to the end of the array while maintaining the relative order of the non-zero elements. Perform the operation in place, without using an extra array.Examples:Input: arr[] = [1, 2, 0, 4, 3, 0, 5, 0]

#### Examples

##### Example 1

- **Output:**
```text
[1, 2, 4, 3, 5, 0, 0, 0]
```
- **Explanation:** The three zeros are moved to the end while the order of the non-zero elements remains unchanged.

##### Example 2

- **Input:**
```text
arr[] = [10, 20, 30]
```
- **Output:**
```text
[10, 20, 30]
```
- **Explanation:** No change in array as there are no 0s.

##### Example 3

- **Input:**
```text
arr[] = [0, 0]
```
- **Output:**
```text
[0, 0]
```
- **Explanation:** No change in array as there are all 0s.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (4)

#### Solution 1 (C++)

- **Submitted:** 2026-10-15 15:29:16
- **Status:** Correct
- **Marks:** 0

```cpp
class Solution {
  public:
    void pushZerosToEnd(vector<int>& arr) {
        int count=0;
        for(int i=0;i<arr.size();i++){
            if(arr[i]!=0)arr[count++]=arr[i];
        }
        while(count<arr.size()){
            arr[count++]=0;
        }
    }
};
```

#### Solution 2 (C++)

- **Submitted:** 2026-10-15 11:51:36
- **Status:** Correct
- **Marks:** 0

```cpp
class Solution:
    def pushZerosToEnd(self, arr: list[int]) -> None:
        count=0;
        for i in range(len(arr)):
            if arr[i]!=0:
                arr[count]=arr[i]
                count+=1
        while(count<len(arr)):
            arr[count]=0
            count+=1
```

#### Solution 3 (C++)

- **Submitted:** 2026-10-15 11:49:17
- **Status:** Correct
- **Marks:** 0

```cpp
class Solution {
    void pushZerosToEnd(int[] arr) {
        int count=0;
        for(int i=0;i<arr.length;i++){
            if(arr[i]!=0)arr[count++]=arr[i];
        }
        while(count<arr.length){
            arr[count++]=0;
        }
        
    }
}
```

#### Solution 4 (C++)

- **Submitted:** 2026-10-15 11:48:27
- **Status:** Correct
- **Marks:** 2

```cpp
class Solution {
  public:
    void pushZerosToEnd(vector<int>& arr) {
        int count=0;
        for(int i=0;i<arr.size();i++){
            if(arr[i]!=0)arr[count++]=arr[i];
        }
        while(count<arr.size()){
            arr[count++]=0;
        }
    }
};
```

*Generated on: 10/15/2026, 3:30:45 PM*