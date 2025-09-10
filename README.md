# dsa-treasure-100
#  Arrays Problems Documentation  

---

## 1. Two Sum  
🔗 [LeetCode 1. Two Sum](https://leetcode.com/problems/two-sum/)  

**Problem:** Find two indices `i, j` such that `nums[i] + nums[j] = target`.  

**Intuition:** Use a hashmap to check if complement exists in O(1).  

**Algorithm:**  
1. Create `unordered_map<int,int> mp`.  
2. Iterate over `nums`:  
   - Compute `need = target - nums[i]`.  
   - If `need` exists in map → return indices `{mp[need], i}`.  
   - Otherwise store `mp[nums[i]] = i`.  

**Complexity:**  
- Time: O(n)  
- Space: O(n)  

**Code reference:** [`two_sum.cpp`](./two_sum.cpp)  

---

## 2. Best Time to Buy and Sell Stock  
🔗 [LeetCode 121. Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)  

**Problem:** Maximize profit with a single buy and sell.  

**Intuition:** Keep track of minimum price so far and compute profit at each step.  

**Algorithm:**  
1. Initialize `minPrice = ∞`, `profit = 0`.  
2. Loop prices:  
   - Update `minPrice = min(minPrice, price)`.  
   - Update `profit = max(profit, price - minPrice)`.  

**Complexity:**  
- Time: O(n)  
- Space: O(1)  

**Code reference:** [`best_time_to_buy_and_sell_stock.cpp`](./best_time_to_buy_and_sell_stock.cpp)  

---

## 3. Maximum Subarray  
🔗 [LeetCode 53. Maximum Subarray](https://leetcode.com/problems/maximum-subarray/)  

**Problem:** Find the contiguous subarray with maximum sum.  

**Intuition:** Use Kadane’s Algorithm → decide at each step whether to extend previous subarray or start new.  

**Algorithm:**  
1. Initialize `currentSum = nums[0]`, `maxSum = nums[0]`.  
2. For each `x` in nums (from index 1):  
   - `currentSum = max(x, currentSum + x)`.  
   - `maxSum = max(maxSum, currentSum)`.  
3. Return `maxSum`.  

**Complexity:**  
- Time: O(n)  
- Space: O(1)  

**Code reference:** [`maximum_subarray.cpp`](./maximum_subarray.cpp)  

---

## 4. Product of Array Except Self  
🔗 [LeetCode 238. Product of Array Except Self](https://leetcode.com/problems/product-of-array-except-self/)  

**Problem:** Return array `output[i] = product of all nums except nums[i]`.  

**Intuition:** Use prefix and suffix product arrays (or do in-place with two passes).  

**Algorithm:**  
1. Create result array `res` with 1’s.  
2. Prefix pass (left → right):  
   - Keep `prefix = 1`.  
   - For each i: `res[i] *= prefix`, then update `prefix *= nums[i]`.  
3. Suffix pass (right → left):  
   - Keep `suffix = 1`.  
   - For each i (reverse): `res[i] *= suffix`, then update `suffix *= nums[i]`.  

**Complexity:**  
- Time: O(n)  
- Space: O(1) (ignoring output array)  

**Code reference:** [`product_except_self.cpp`](./product_except_self.cpp)  

---

## 5. Maximum Product Subarray  
🔗 [LeetCode 152. Maximum Product Subarray](https://leetcode.com/problems/maximum-product-subarray/)  

**Problem:** Find contiguous subarray with maximum product.  

**Intuition:** Product can flip sign → need to track both max and min at each step.  

**Algorithm:**  
1. Initialize `curMax = curMin = ans = nums[0]`.  
2. For each `x` in nums (from index 1):  
   - If `x < 0`, swap(`curMax`, `curMin`).  
   - Update `curMax = max(x, curMax * x)`.  
   - Update `curMin = min(x, curMin * x)`.  
   - Update `ans = max(ans, curMax)`.  
3. Return `ans`.  

**Complexity:**  
- Time: O(n)  
- Space: O(1)  

**Code reference:** [`maximum_product_subarray.cpp`](./maximum_product_subarray.cpp)  

---
