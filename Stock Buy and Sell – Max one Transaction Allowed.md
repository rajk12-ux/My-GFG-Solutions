## 01. Stock Buy and Sell – Max one Transaction Allowed

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/buy-stock-2/1)

### Problem Description

**Task:** Given an array prices[] of non-negative integers, representing the prices of the stocks on different days. The task is to find the maximum profit possible by buying and selling the stocks on different days when at most one transaction is allowed. Here one transaction means 1 buy + 1 Sell. If it is not possible to make a profit then return 0.

> **Note:** Stock must be bought before being sold.

#### Examples

##### Example 1

- **Input:**
```text
prices[] = [7, 10, 1, 3, 6, 9, 2]Output: 8Explanation: You can buy the stock on day 2 at price = 1 and sell it on day 5 at price = 9. Hence, the profit is 8.
```

##### Example 2

- **Input:**
```text
prices[] = [7, 6, 4, 3, 1]Output: 0 Explanation: Here the prices are in decreasing order, hence if we buy any day then we cannot sell it at a greater price. Hence, the answer is 0.
```

##### Example 3

- **Input:**
```text
prices[] = [1, 3, 6, 9, 11]Output: 10 Explanation: Since the array is sorted in increasing order, we can make maximum profit by buying at price[0] and selling at price[n-1].
```

#### Constraints

- **1.** `1 ≤ prices.size() ≤ 10⁵⁰ ≤ prices[i] ≤ 10⁴`

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (3)

#### Solution 1 (Python)

- **Submitted:** 2026-10-20 11:02:25
- **Status:** Correct
- **Marks:** 0

```python
class Solution:
    def maxProfit(self, prices):
        min_till_now=prices[0];
        maxprof=0;
        for i in range(1,len(prices)):
            min_till_now=min(min_till_now,prices[i])
            maxprof=max(maxprof,prices[i]-min_till_now)
        return maxprof;
```

#### Solution 2 (Python)

- **Submitted:** 2026-10-20 11:00:45
- **Status:** Correct
- **Marks:** 0

```python
class Solution {
    public int maxProfit(int[] prices) {
        int min_till_now=prices[0];
        int maxprof=0;
        for(int i=1;i<prices.length;i++){
            min_till_now=Math.min(min_till_now,prices[i]);
            maxprof=Math.max(maxprof,prices[i]-min_till_now);
        }
        return maxprof;
        
    }
}
```

#### Solution 3 (Python)

- **Submitted:** 2026-10-20 10:59:29
- **Status:** Correct
- **Marks:** 2

```python
class Solution {
  public:
    int maxProfit(vector<int> &prices) {
        int min_till_now=prices[0];
        int maxprof=0;
        for(int i=1;i<prices.size();i++){
            min_till_now=min(min_till_now,prices[i]);
            maxprof=max(maxprof,prices[i]-min_till_now);
        }
        return maxprof;
    }
};
```

*Generated on: 10/20/2026, 11:03:03 AM*