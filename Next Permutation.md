## 01. Next Permutation

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/next-permutation5226/1)

### Problem Description

**Task:** Given an array of integers arr[] representing a permutation, implement the next permutation that rearranges the numbers into the lexicographically smallest greater (or next) permutation.
If no next permutation exists, rearrange the numbers into the lowest possible order (i.e., sorted in ascending order).

#### Examples

##### Example 1

- **Input:**
```text
arr[] = [2, 4, 1, 7, 5, 0]
```
- **Output:**
```text
[2, 4, 5, 0, 1, 7]
```
- **Explanation:** The next permutation of the given array is [2, 4, 5, 0, 1, 7].

##### Example 2

- **Input:**
```text
arr[] = [3, 2, 1]
```
- **Output:**
```text
[1, 2, 3]
```
- **Explanation:** As arr[] is the last permutation, the next permutation is the lowest one.

##### Example 3

- **Input:**
```text
arr[] = [3, 4, 2, 5, 1]
```
- **Output:**
```text
[3, 4, 5, 1, 2]
```
- **Explanation:** The next permutation of the given array is [3, 4, 5, 1, 2].

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (3)

#### Solution 1 (Python)

- **Submitted:** 2026-10-19 09:37:16
- **Status:** Correct
- **Marks:** 0

```python
class Solution:
    def nextPermutation(self, arr):
        br=-1
        for i in range(len(arr)-1,-1,-1):
            if arr[i]>arr[i-1]:
                br=i-1
                break
        if br==-1:
            arr.reverse()
        else:
            for i in range(len(arr)-1,br-1,-1):
                if arr[i]>arr[br]:
                    arr[br],arr[i]=arr[i],arr[br]
                    break
            arr[br+1::]=arr[br+1::][::-1]
```

#### Solution 2 (Python)

- **Submitted:** 2026-10-19 09:24:50
- **Status:** Correct
- **Marks:** 0

```python
class Solution {
    void nextPermutation(int[] arr) {
        int br=-1;
        for(int i=arr.length-1;i>0;i--){
            if(arr[i]>arr[i-1]){
                br=i-1;
                break;
            }
        }
        if(br==-1){
            for(int i=0;i<arr.length/2;i++){
                arr[i]=arr[i]^arr[arr.length-1-i];
                arr[arr.length-i-1]=arr[i]^arr[arr.length-1-i];
                arr[i]=arr[i]^arr[arr.length-1-i];
            }
        }
        else{
            for(int i=arr.length-1;i>br;i--){
                if(arr[i]>arr[br]){
                    arr[br]=arr[i]^arr[br];
                    arr[i]=arr[i]^arr[br];
                    arr[br]=arr[i]^arr[br];
                    break;
                }
            }
            for(int i=br+1;i<br+1+(arr.length-br-1)/2;i++){
                arr[i]=arr[i]^arr[arr.length-i+br];
                arr[arr.length-i+br]=arr[i]^arr[arr.length-i+br];
                arr[i]=arr[i]^arr[arr.length-i+br];
            }
        }
        
    }
}
```

#### Solution 3 (Python)

- **Submitted:** 2026-10-16 13:58:56
- **Status:** Correct
- **Marks:** 4

```python
class Solution {
  public:
    void nextPermutation(vector<int>& arr) {
            int br=-1;
            for(int i=arr.size()-1;i>0;i--){
                if(arr[i]>arr[i-1]){
                    br=i-1;
                    break;
                }
            }
            if(br==-1)reverse(arr.begin(),arr.end());
            else{
                for(int i=arr.size()-1;i>br;i--){
                    if(arr[i]>arr[br]){
                        swap(arr[br],arr[i]);
                        break;
                    }
                }
                reverse(arr.begin()+br+1,arr.end());
            }
        }
};
```

*Generated on: 10/19/2026, 9:39:31 AM*