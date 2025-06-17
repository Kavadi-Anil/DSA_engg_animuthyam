# Finding the Maximum Sum of a Contiguous Subarray of Fixed Length in Python

## Problem Description

Given a list of integers, find the maximum sum among all contiguous subarrays of a specified length (here, length 3).  
Below are two approaches:
1. **Brute Force Approach** using nested loops.
2. **Sliding Window Approach** (optimized).

---

## Input

No user input required; the list and subarray length are hardcoded as:
- `[5, 9, 1, 8, 0]`
- Subarray length = 3

---

## 1. Brute Force Approach (Nested Loops)

```python
num = [5, 9, 1, 8, 0]
L = len(num) 
summ = 0 
maxx = 0 
lenth_of_sum = 3

for i in range(L):
    for j in range(i, L): 
        list = []
        for K in range(i, j + 1):  
            list = list + [num[K]] 
        if len(list) == lenth_of_sum:
            summ = sum(list) 
            maxx = max(summ, maxx) 
print(maxx)
```

**Explanation:**  
- Generates all possible contiguous subarrays.
- For each subarray of the required length (3), computes its sum and updates the maximum.
- **Time Complexity:** O(n²) – less efficient for large lists.

---

## 2. Sliding Window Approach (Optimized)

```python
li = [5, 9, 1, 8, 0]
L = len(li) 
temp = 0 
l = 0 
maxx = 0
for r in range(L): 
    temp = temp + li[r] 
    if (r - l) == 3:       # If window size is greater than 3, slide the window
        temp = temp - li[l] 
        l = l + 1 
    if (r - l + 1) == 3:   # When window size is exactly 3
        maxx = max(temp, maxx) 
print(maxx)
```

**Explanation:**  
- Maintains a "window" of length 3 and slides it across the list.
- Adds the new rightmost element and removes the leftmost element from the sum as the window moves.
- Updates the maximum sum when the window size is exactly 3.
- **Time Complexity:** O(n) – much more efficient for large lists.

---

## Output

```
18
18
```

*In both approaches, the maximum sum for any contiguous subarray of length 3 is **18** (`[9, 1, 8]`).*

---

## Conclusion

- The **brute force method** checks every possible subarray, which is simple but slow for big lists.
- The **sliding window approach** is optimized, using previous computations to achieve a linear time solution (**O(n)**).  
**Sliding window is recommended for efficiency.**