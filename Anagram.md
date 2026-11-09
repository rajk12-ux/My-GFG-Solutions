## 01. Anagram

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/anagram-1587115620/1)

### Problem Description

**Task:** Given two non-empty strings s1 and s2, consisting only of lowercase English letters, determine whether they are anagrams of each other or not. Two strings are considered anagrams if they contain the same characters with exactly the same frequencies, regardless of their order.Examples:Input: s1 = "geeks" s2 = "kseeg"Output: true Explanation: Both the string have same characters with same frequency. So, they are anagrams.Input: s1 = "allergy", s2 = "allergyy" Output: false Explanation: Although the characters are mostly the same, s2 contains an extra 'y' character. Since the frequency of characters differs, the strings are not anagrams. Input: s1 = "listen", s2 = "lists" Output: false Explanation: The characters in the two strings are not the same — some are missing or extra. So, they are not anagrams.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n + m)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (3)

#### Solution 1 (Python)

- **Submitted:** 2026-11-09 12:33:45
- **Status:** Correct
- **Marks:** 0

```python
class Solution:
    def areAnagrams(self, s1, s2):
        freq1=[0]*26
        freq2=[0]*26
        for c in s1:
            freq1[ord(c)-ord('a')]+=1
        for c in s2:
            freq2[ord(c)-ord('a')]+=1
        for i in range(0,26):
            if freq1[i]!=freq2[i]:
                return False
        return True
```

#### Solution 2 (Python)

- **Submitted:** 2026-11-09 12:28:30
- **Status:** Correct
- **Marks:** 0

```python
class Solution {
    public static boolean areAnagrams(String s1, String s2) {
        int[] freq1 = new int[26];
        int[] freq2 = new int[26];
        
        for (char c : s1.toCharArray()) {
            ++freq1[c - 'a'];
        }
        
        for (char c : s2.toCharArray()) {
            ++freq2[c - 'a'];
        }
        
        for (int i = 0; i < 26; i++) {
            if (freq1[i] != freq2[i]) return false;
        }
        
        return true;
    }
}
```

#### Solution 3 (Python)

- **Submitted:** 2026-11-09 12:24:42
- **Status:** Correct
- **Marks:** 2

```python
class Solution {
  public:
    bool areAnagrams(string& s1, string& s2) {
        vector<int> freq1(26,0);
        vector<int> freq2(26,0);
        for(char c:s1){
            ++freq1[c-'a'];
        }
        for(char c:s2){
            ++freq2[c-'a'];
        }
        for(int i=0;i<26;i++){
            if(freq1[i]!=freq2[i])return false;
        }
        return true;
    }
};
```

*Generated on: 11/9/2026, 12:34:21 PM*