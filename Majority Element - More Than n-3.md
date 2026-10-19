## 01. Majority Element - More Than n/3

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/majority-vote/1)

### Problem Description

**Task:** Given an array arr[] consisting of n integers, find all the array elements which occurs more than floor(n/3) times. Return the resulting array in strictly increasing order. If no such elements exist, return an empty array.Examples:Input: arr[] = [2, 2, 3, 1, 3, 2, 1, 1]

#### Examples

##### Example 1

- **Output:**
```text
[-5]Explanation: The frequency of -5 is 2, which is more than floor n/3 (3/3 = 1).Input: arr[] = [3, 2, 2, 4, 1, 4]Output: []Explanation: There is no majority element.
```
- **Explanation:** The frequency of 1 and 2 is 3, which is more than floor n/3 (8/3 = 2).Input: arr[] = [-5, 3, -5]

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (3)

#### Solution 1 (Python)

- **Submitted:** 2026-10-19 14:56:45
- **Status:** Correct
- **Marks:** 0

```python
class Solution:
    def findMajority(self, arr):
        el1=0
        el2=0
        c1=0
        c2=0
        for i in arr:
            if i==el1:
                c1+=1
            elif i==el2:
                c2+=1
            elif c1==0:
                el1=i
                c1=1
            elif c2==0:
                el2=i
                c2=1
            else:
                c1-=1
                c2-=1
        c1=0
        c2=0
        for i in arr:
            if i==el1:
                c1+=1
            elif i==el2:
                c2+=1
        ans=[]
        if c1>len(arr)/3:
            ans.append(el1)
        if c2>len(arr)/3:
            ans.append(el2)
        if len(ans)==2 and el1>el2:
            ans[0],ans[1]=ans[1],ans[0]
        return ans
```

#### Solution 2 (Python)

- **Submitted:** 2026-10-19 12:32:42
- **Status:** Correct
- **Marks:** 0

```python
class Solution {
    public ArrayList<Integer> findMajority(int[] arr) {
        int el1=0,el2=0,c1=0,c2=0;
        for(int i:arr){
            if(i==el1)++c1;
            else if(i==el2)++c2;
            else if(c1==0){
                el1=i;
                c1=1;
            }
            else if(c2==0){
                el2=i;
                c2=1;
            }
            else{
                --c1;
                --c2;
            }
        }
        c1=0;
        c2=0;
        for(int i:arr){
            if(i==el1)++c1;
            else if(i==el2)++c2;
        }
        ArrayList<Integer> ans=new ArrayList<Integer>();
        if(c1>arr.length/3)ans.add(el1);
        if(c2>arr.length/3)ans.add(el2);
        if(ans.size()==2 && el1>el2){
            ans.set(0,ans.get(0)^ans.get(1));
            ans.set(1,ans.get(0)^ans.get(1));
            ans.set(0,ans.get(0)^ans.get(1));
        }
        return ans;
        
    }
}
```

#### Solution 3 (Python)

- **Submitted:** 2026-10-19 12:23:01
- **Status:** Correct
- **Marks:** 4

```python
class Solution {
  public:
    vector<int> findMajority(vector<int>& arr) {
        int el1=INT_MAX,el2=INT_MAX,c1=0,c2=0;
        for(int i:arr){
            if(i==el1)++c1;
            else if(i==el2)++c2;
            else if(c1==0){
                el1=i;
                c1=1;
            }
            else if(c2==0){
                el2=i;
                c2=1;
            }
            else{
                --c1;
                --c2;
            }
        }
        c1=0,c2=0;
        for(int i:arr){
            if(i==el1)++c1;
            else if(i==el2)++c2;
        }
        vector<int> ans;
        if(c1>arr.size()/3)ans.push_back(el1);
        if(c2>arr.size()/3)ans.push_back(el2);
        if(ans.size()==2 && el1>el2)swap(ans[0],ans[1]);
        return ans;
    }
};
```

*Generated on: 10/19/2026, 2:57:11 PM*