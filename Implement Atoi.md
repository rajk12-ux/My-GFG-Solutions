## 01. Implement Atoi

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/implement-atoi/1)

### Problem Description

**Task:** Given a string s, convert it into a 32-bit signed integer (similar to the atoi() function) without using any built-in conversion functions.The conversion follows these rules:Ignore Leading Whitespaces: Skip all leading whitespace characters.Check Sign: If the next character is either '+' or '-', take it as the sign of the number. If no sign is present, assume the number is positive.Read Digits: Read the digits and ignore any leading zeros. Stop reading when a non-digit character is encountered or the end of the string is reached. If no digits are found, return 0.Handle Overflow: If the number exceeds the range of a 32-bit signed integer:Return 2³¹ − 1 (i.e., 2147483647) if it is greater than the maximum value.Return −2³¹ (i.e., -2147483648) if it is smaller than the minimum value.Return the final integer value.Examples:Input: s = "-123"

#### Examples

##### Example 1

- **Output:**
```text
2147483647Explanation: The converted number will be greater than 2³¹ – 1, therefore print 2³¹ – 1 = 2147483647.
```

##### Example 2

- **Input:**
```text
s = "-999999999999"
```
- **Output:**
```text
-12
```
- **Explanation:** Nothing is read after -12 as a non-digit character ‘g’ was encountered.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (3)

#### Solution 1 (Python)

- **Submitted:** 2026-11-04 10:36:52
- **Status:** Correct
- **Marks:** 0

```python
class Solution:
    def myAtoi(self, s):
        pos=True #positive
        ans=0
        curr=0
        maxx=2147483647
        for curr in range(0,len(s)):
            if  s[curr]=='-':
                pos=False
                break
            
            elif  s[curr]=='+':
                break
            
            elif  s[curr]>='0' and s[curr]<='9' :
                curr-=1
                break
            
        
        for i in range(curr+1,len(s)):
            if  s[i]>='0' and s[i]<='9':
                dig=int(s[i])
                if  ans>(maxx-dig)/10:
                    if  pos==True:
                        return maxx
                    
                    else:
                        return -(maxx+1)
                    
                
                ans = ans*10+dig
            
            else :
                break
            
        
        if  pos==False:
            ans = -ans
        
        return ans
```

#### Solution 2 (Python)

- **Submitted:** 2026-11-04 10:25:59
- **Status:** Correct
- **Marks:** 0

```python
class Solution {
    public int myAtoi(String s) {
        boolean pos=true;//positive
        int ans=0,curr=0;
        for(;curr<s.length();curr++){
            if(s.charAt(curr)=='-'){
                pos=false;
                break;
            }
            else if(s.charAt(curr)=='+'){
                break;
            }
            else if((s.charAt(curr)>='0' && s.charAt(curr)<='9')){
                --curr;
                break;
            }
        }
        for(int i=curr+1;i<s.length();i++){
            if(s.charAt(i)>='0' && s.charAt(i)<='9'){
                int dig=s.charAt(i)-'0';
                if(ans>(Integer.MAX_VALUE-dig)/10){
                    if(pos){
                        return Integer.MAX_VALUE;
                    }
                    else{
                        return Integer.MIN_VALUE;
                    }
                }
                ans = ans*10+dig;
            }
            else {
                break;
            }
        }
        if(!pos){
            ans = -ans;
        }
        return ans;
    }
}
```

#### Solution 3 (Python)

- **Submitted:** 2026-11-04 10:16:11
- **Status:** Correct
- **Marks:** 4

```python
class Solution {
  public:
    int myAtoi(string &s) {
        bool pos=true;//positive
        int ans=0,curr=0;
        for(;curr<s.size();curr++){
            if(s[curr]=='-'){
                pos=false;
                break;
            }
            else if(s[curr]=='+'){
                break;
            }
            else if((s[curr]>='0' && s[curr]<='9')){
                --curr;
                break;
            }
        }
        for(int i=curr+1;i<s.size();i++){
            if(s[i]>='0' && s[i]<='9'){
                int dig=s[i]-'0';
                
                if(ans>(INT_MAX-dig)/10){
                    if(pos){
                        return INT_MAX;
                    }
                    else{
                        return INT_MIN;
                    }
                }
                ans = ans*10+dig;
            }
            else {
                break;
            }
        }
        if(!pos){
            ans = -ans;
        }
        return ans;
    }
};
```

*Generated on: 11/4/2026, 10:37:52 AM*