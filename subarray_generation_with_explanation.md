# Generating All Contiguous Subarrays of a List in Python

## Problem Description

Given a list of integers, generate all possible contiguous subarrays (also called "slices" or "segments"). A contiguous subarray contains elements that are consecutive in the original list. Print all such subarrays as a list of lists.

## Input

No user input is required; the list `num` is hardcoded as `[1, 2, 3]`.

## Code with Explanation

```python
num = [1, 2, 3]         # The original list
n = len(num)            # Find the length of the list
ans = []                # This will store all subarrays

for i in range(n):
    for j in range(i, n):          # j goes from the current i to the end of the list
        temp = []
        for k in range(i, j + 1):  # For each pair (i, j), collect elements from index i to j (inclusive)
            temp.append(num[k])
        ans.append(temp)           # Add this subarray to the answer list

print(ans)                        # Print all contiguous subarrays
```

### How It Works

- The outer loop picks the starting index `i` of the subarray.
- The next loop picks the ending index `j` (where `j >= i`).
- For every such pair `(i, j)`, another loop collects all elements from index `i` to `j` and stores them in a temporary list `temp`.
- Each `temp` is added to the answer list `ans`.
- Finally, all possible contiguous subarrays are printed.

## Output

```
[[1], [1, 2], [1, 2, 3], [2], [2, 3], [3]]
```

*Explanation of Output:*  
These are all possible contiguous subarrays of `[1, 2, 3]`:
- `[1]`
- `[1, 2]`
- `[1, 2, 3]`
- `[2]`
- `[2, 3]`
- `[3]`