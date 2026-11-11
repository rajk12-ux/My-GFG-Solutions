## 01. Non Repeating Character

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/non-repeating-character-1587115620/1)

### Problem Description

**Task:** Given a string s consisting of lowercase English Letters. return the first non-repeating character in s. If there is no non-repeating character, return '$'.Examples:Input: s = "geeksforgeeks"

#### Examples

##### Example 1

- **Output:**
```text
'f'
```
- **Explanation:** In the given string, 'f' is the first character in the string which does not repeat.Input: s = "racecar"Output: 'e'Explanation: In the given string, 'e' is the only character in the string which does not repeat.Input: s = "aabbccc"Output: '$'Explanation: All the characters in the given string are repeating.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (3)

#### Solution 1 (Python)

- **Submitted:** 2026-11-11 15:46:47
- **Status:** Correct
- **Marks:** 0

```python
class Solution:
    def nonRepeatingChar(self,s):
        freq=[0]*26;
        for c in s:
            freq[ord(c)-ord('a')]+=1
        
        for c in s:
            if(freq[ord(c)-ord('a')]==1):
                return c
        
        return '$'
```

#### Solution 2 (Python)

- **Submitted:** 2026-11-11 15:44:30
- **Status:** Correct
- **Marks:** 0

```python
class Solution {
    public char nonRepeatingChar(String s) {
        int freq[]=new int[26];
        for(char c:s.toCharArray()){
            ++freq[c-'a'];
        }
        for(char c:s.toCharArray()){
            if(freq[c-'a']==1)return c;
        }
        return '$';
    }
}
```

#### Solution 3 (Python)

- **Submitted:** 2026-11-11 15:43:09
- **Status:** Correct
- **Marks:** 2

```python
class Solution {
  public:
    char nonRepeatingChar(string &s) {
        int freq[26]={0};
        for(char c:s){
            ++freq[c-'a'];
        }
        for(char c:s){
            if(freq[c-'a']==1)return c;
        }
        return '$';
    }
};
```

*Generated on: 11/11/2026, 3:47:27 PM*