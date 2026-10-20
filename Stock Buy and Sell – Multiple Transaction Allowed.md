## 01. Stock Buy and Sell – Multiple Transaction Allowed

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/stock-buy-and-sell2615/1)

### Problem Description

**Task:** Given an integer array prices[], where prices[i] is the price of a given stock on the ith day. Each day you may decide to either buy or sell the stock at price[i], you can even buy and sell the stock on the same day, return the maximum profit that you can get.Note: A stock can only be sold if it has been bought previously and multiple stocks cannot be held on any given day.Examples:Input: prices[] = [100, 180, 260, 310, 40, 535, 695]Output: 865Explanation: Buy the stock on day 0 and sell it on day 3 = > 310 – 100 = 210. Buy the stock on day 4 and sell it on day 6 = > 695 – 40 = 655. Maximum Profit = 210 + 655 = 865.Input: prices[] = [4, 2, 2, 2, 4]Output: 2Explanation: Buy the stock on day 3 and sell it on day 4 = > 4 – 2 = 2. Maximum Profit = 2.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (3)

#### Solution 1 (Python)

- **Submitted:** 2026-10-20 10:41:25
- **Status:** Correct
- **Marks:** 0

```python
class Solution:
    def maxProfit(self, prices):
        maxprof=0
        for i in range(1,len(prices)):
            if prices[i]>prices[i-1]:
                maxprof+=(prices[i]-prices[i-1])
        return maxprof
```

#### Solution 2 (Python)

- **Submitted:** 2026-10-20 10:39:27
- **Status:** Correct
- **Marks:** 0

```python
class Solution {
    public int maxProfit(int[] prices) {
        int maxprof=0;
        for(int i=1;i<prices.length;i++){
            if(prices[i]>prices[i-1])maxprof+=(prices[i]-prices[i-1]);
        }
        return maxprof;
        
    }
}
```

#### Solution 3 (Python)

- **Submitted:** 2026-10-20 10:38:22
- **Status:** Correct
- **Marks:** 4

```python
class Solution {
  public:
    int maxProfit(vector<int> &prices) {
        int maxprof=0;
        for(int i=1;i<prices.size();i++){
            if(prices[i]>prices[i-1])maxprof+=(prices[i]-prices[i-1]);
        }
        return maxprof;
    }
};
```

*Generated on: 10/20/2026, 10:41:50 AM*