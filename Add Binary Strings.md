## 01. Add Binary Strings

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/add-binary-strings3805/1)

### Problem Description

**Task:** Given two binary strings s1 and s2 consisting of only 0s and 1s. Find the resultant string after adding the two Binary Strings.Note: The input strings may contain leading zeros but the output string should not have any leading zeros.

#### Examples

##### Example 1

- **Input:**
```text
s1 = "1101", s2 = "111"
```
- **Output:**
```text
10100 1101 + 111 10100
```

##### Example 2

- **Input:**
```text
s1 = "00100", s2 = "010"
```
- **Output:**
```text
110 100 + 10 110
```

#### Constraints

- **1.** `1 ≤s1.size(), s2.size()≤ 10⁶`

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(n)

### Accepted Solutions (3)

#### Solution 1 (Python)

- **Submitted:** 2026-11-06 18:23:31
- **Status:** Correct
- **Marks:** 0

```python
class Solution:
    def addBinary(self, s1, s2):
        a = list(s1[::-1].rstrip('0')) 
        b = list(s2[::-1].rstrip('0'))

        if len(a) < len(b):
            a, b = b, a
        for i in range(len(b),len(a)):
            b.append('0')
        ans = []
        c = 0

        for i in range(len(a)):
            x = int(a[i])
            y = int(b[i]) 

            total = x + y + c

            ans.append(str(total % 2))
            c = total // 2

        if c == 1:
            ans.append('1')

        return ''.join(ans[::-1])
```

#### Solution 2 (Python)

- **Submitted:** 2026-11-06 17:46:03
- **Status:** Correct
- **Marks:** 0

```python
class Solution {
    public String addBinary(String s1, String s2) {
        StringBuilder a = new StringBuilder(s1).reverse();
        StringBuilder b = new StringBuilder(s2).reverse();

        while (a.length() > 1 && a.charAt(a.length()-1) == '0')
            a.deleteCharAt(a.length()-1);

        while (b.length() > 1 && b.charAt(b.length()-1) == '0')
            b.deleteCharAt(b.length()-1);

        if (a.length() < b.length()) {
            StringBuilder temp = a;
            a = b;
            b = temp;
        }

        StringBuilder ans = new StringBuilder();
        int c = 0;

        for (int i = 0; i < a.length(); i++) {
            int x = a.charAt(i) - '0';
            int y = (i < b.length()) ? b.charAt(i) - '0' : 0;

            int sum = x + y + c;

            ans.append(sum % 2);
            c = sum / 2;
        }

        if (c == 1) ans.append('1');

        return ans.reverse().toString();
    }
}
```

#### Solution 3 (Python)

- **Submitted:** 2026-11-06 17:24:27
- **Status:** Correct
- **Marks:** 4

```python
class Solution {
public:
    string addBinary(string& s1, string& s2) {
        string a=s1, b=s2;

        reverse(a.begin(),a.end());
        reverse(b.begin(),b.end());
        
        while(a[a.size()-1]=='0')a.pop_back();
        while(b[b.size()-1]=='0')b.pop_back();

        if(a.size()<b.size()) swap(a,b);

        string ans="";
        int c=0;

        for(int i=0;i<a.size();i++){
            int x=a[i]-'0';
            int y=(i<b.size()) ? b[i]-'0' : 0;

            int sum=x+y+c;

            ans.push_back('0'+(sum%2));
            c=sum/2;
        }

        if(c==1) ans.push_back('1');

        reverse(ans.begin(),ans.end());

        return ans;
    }
};
```

*Generated on: 11/6/2026, 6:24:17 PM*