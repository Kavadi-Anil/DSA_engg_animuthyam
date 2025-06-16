# Coding Problems: Working with Sets in Python

---

## 1. Basic Set Operations

**Question:**  
Given a set, perform add and remove operations. Demonstrate that sets do not accept duplicate values. Then, convert a list with repeated elements to a set and print the result.

**Sample Input:**  
*(Input is hardcoded, no user input required)*

**Code:**
```python
s = {5, 6}
s.add(7)
s.remove(6)
s.add(5)  # set does not accept duplicates
print(s)
a = [1, 3, 3]
b = set(a)
print(b)
```

**Sample Output:**
```
{5, 7}
{1, 3}
```

---

## 2. Iterating Over Lists and Sets

**Question:**  
Given a list and a set (both potentially with duplicate elements), print each element by iterating through them. Observe the difference in output.

**Note on Time Complexity:**  
- Iterating over a list takes **O(n)** time, where n is the number of elements.
- Iterating over a set also takes **O(n)** time, but **searching for an element** in a set is faster (**O(1)** on average) compared to a list (**O(n)**).
- **Sets are generally faster than lists for membership checks** due to their underlying hash table implementation.

**Sample Input:**  
*(Input is hardcoded, no user input required)*

**Code:**
```python
lst = [1, 2, 2, 3, 44]
for i in lst:
    print(i)

st = {1, 23, 3, 4, 4, 4}
for j in st:
    print(j)
```

**Sample Output:**
```
1
2
2
3
44
1
3
4
23
```
*(Note: Set output order may vary, and duplicates are removed.)*

---

## 3. Find Duplicate and Missing Number in a List

**Question:**  
Given a list of integers where one number appears twice and one number is missing from 1 to n (where n is the length of the list), find and print the duplicate and the missing numbers.

**Sample Input:**  
*(Input is hardcoded, no user input required)*

**Code:**
```python
nums = [1, 2, 2, 4]   
L = len(nums)  
duplicate = 0
empty_set = set() 
print(empty_set)
for i in range(L):
    if nums[i] not in empty_set:
        empty_set.add(nums[i])
    else: 
        duplicate = nums[i] 
print(empty_set) 
for i in range(1, L+1):
    if i not in empty_set:
        missing = i 
print(duplicate, missing)
```

**Sample Output:**
```
set()
{1, 2, 4}
2 3
```
*(Explanation: Duplicate is 2, missing is 3)*

---