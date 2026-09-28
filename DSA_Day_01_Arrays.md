# DSA Day 01 - Arrays

**Date:** September 28, 2026  
**Topic:** Arrays  
**Focus:** Arrays fundamentals + frequency counting

---

## 1. Basic Traversal

### Question
Given `nums = [10, 20, 30, 40, 50]`, print every element.

### My Answer
```python
for num in nums:
    print(num)
```

**Status:** ✅ Correct

---

## 2. Index-Based Traversal

### Question
Given `nums = [10, 20, 30, 40, 50]`, print only elements at even indexes.

Expected:
```text
10
30
50
```

### My Answer
```python
for i in range(0, len(nums), 2):
    print(nums[i])
```

**Status:** ✅ Correct

---

## 3. Accumulator

### Question
Given `nums = [10, 20, 5, 15]`, calculate the sum using a loop. Do not use `sum()`.

### My Answer
```python
s = 0
for i in nums:
    s += i
print(s)
```

**Output:** `50`

**Status:** ✅ Correct

### Pattern
```python
result = initial_value
for item in collection:
    result += item
```

---

## 4. Counting

### Question
Given `nums = [10, 15, 20, 25, 30, 35]`, count numbers greater than `20`.

### My Answer
```python
c = 0
for i in nums:
    if i > 20:
        c += 1
print(c)
```

**Output:** `3`

**Status:** ✅ Correct

---

## 5. Maximum

### Question
Given `nums = [42, 17, 8, 91, 23, 56]`, find the largest number without `max()` or sorting.

### My Answer
```python
m = nums[0]
for i in nums:
    if i > m:
        m = i
print(m)
```

**Output:** `91`

**Status:** ✅ Correct

### Key Learning
Initialize from `nums[0]`, not `0`, so negative arrays also work.

---

## 6. Minimum

### Question
Given `nums = [42, 17, 8, 91, 23, 56]`, find the smallest number without `min()` or sorting.

### My Answer
```python
m = nums[0]
for i in nums:
    if i < m:
        m = i
print(m)
```

**Output:** `8`

**Status:** ✅ Correct

---

## 7. Searching

### Question
Given `nums = [12, 7, 25, 4, 18, 9]` and `target = 25`, print `Found` if it exists, otherwise `Not Found`. Do not use `in` or `.index()`.

### First Attempt
```python
for i in nums:
    if i == target:
        print("found")
```

### Problem
If the target does not exist, nothing is printed.

### Corrected Answer
```python
found = False

for i in nums:
    if i == target:
        found = True

if found:
    print("found")
else:
    print("not found")
```

**Status:** ✅ Correct after correction

### Key Learning
This is the boolean **flag pattern**.

---

## 8. Filtering

### Question
Given `nums = [12, 7, 25, 4, 18, 9]`, print only numbers greater than `10`.

### My Answer
```python
for i in nums:
    if i > 10:
        print(i)
```

**Output:**
```text
12
25
18
```

**Status:** ✅ Correct

---

## 9. Transformation

### Question
Given `nums = [2, 4, 6, 8]`, create a new list where every number is multiplied by `2`.

### My Answer
```python
n = []
for i in nums:
    i = i * 2
    n.append(i)
```

**Output:** `[4, 8, 12, 16]`

**Status:** ✅ Correct

### Cleaner Version
```python
result = []
for i in nums:
    result.append(i * 2)
```

---

## 10. Frequency Counting

### Question
Given `nums = [2, 3, 2, 5, 3, 2, 7]`, create a dictionary containing each number's frequency.

### My Answer
```python
freq = {}

for i in nums:
    if i in freq:
        freq[i] += 1
    else:
        freq[i] = 1
```

### Output
```python
{2: 3, 3: 2, 5: 1, 7: 1}
```

**Status:** ✅ Correct

### Pattern
```text
Does key exist?
  YES -> increment
  NO  -> initialize to 1
```

---

## 11. Most Frequent Number

### Question
Given `nums = [4, 1, 4, 2, 1, 4, 3, 2]`, find the most frequent number.

### My Answer
```python
freq = {}

for i in nums:
    if i in freq:
        freq[i] += 1
    else:
        freq[i] = 1

freq_h = 0

for i, j in freq.items():
    if j > freq_h:
        freq_h = j
        num = i

print(num)
```

**Output:** `4`

**Status:** ✅ Correct

### Key Learning
This combines:
1. Frequency counting
2. Maximum tracking

---

## 12. Most Frequent Number - Independent Attempt

### Question
Given `nums = [5, 2, 5, 3, 2, 5, 3, 3]`, find the most frequent number.

### My Answer
```python
freq = {}

for i in nums:
    if i in freq:
        freq[i] += 1
    else:
        freq[i] = 1

freq_h = 0

for i, j in freq.items():
    if j > freq_h:
        freq_h = j
        num = i

print(num)
```

**Output:** `5`

**Status:** ✅ Correct independently

---

## 13. Elements Appearing Exactly Once

### Question
Given `nums = [4, 1, 4, 2, 1, 4, 3, 2, 5]`, print numbers that appear exactly once.

### My Answer
```python
freq = {}

for i in nums:
    if i in freq:
        freq[i] += 1
    else:
        freq[i] = 1

for i, j in freq.items():
    if j == 1:
        print(i)
```

**Output:**
```text
3
5
```

**Status:** ✅ Correct

---

# Day 01 Pattern Summary

| # | Pattern | Status |
|---|---|---|
| 1 | Basic Traversal | ✅ |
| 2 | Index Traversal | ✅ |
| 3 | Accumulator | ✅ |
| 4 | Counting | ✅ |
| 5 | Maximum | ✅ |
| 6 | Minimum | ✅ |
| 7 | Searching | ✅ |
| 8 | Filtering | ✅ |
| 9 | Transformation | ✅ |
| 10 | Frequency Counting | ✅ |
| 11 | Most Frequent Element | ✅ |
| 12 | Exactly Once | ✅ |

---

# Core Templates

## Traversal
```python
for item in nums:
    ...
```

## Index Traversal
```python
for i in range(len(nums)):
    ...
```

## Accumulator
```python
result = 0
for item in nums:
    result += item
```

## Counting
```python
count = 0
for item in nums:
    if condition:
        count += 1
```

## Min / Max
```python
value = nums[0]
for item in nums:
    if item > value:
        value = item
```

## Searching
```python
found = False
for item in nums:
    if item == target:
        found = True
```

## Filtering
```python
for item in nums:
    if condition:
        print(item)
```

## Transformation
```python
result = []
for item in nums:
    result.append(transform(item))
```

## Frequency
```python
freq = {}

for item in nums:
    if item in freq:
        freq[item] += 1
    else:
        freq[item] = 1
```

---

# Complexity Notes

| Pattern | Time | Extra Space |
|---|---:|---:|
| Traversal | O(n) | O(1) |
| Index traversal | O(n) | O(1) |
| Accumulator | O(n) | O(1) |
| Counting | O(n) | O(1) |
| Min / Max | O(n) | O(1) |
| Searching | O(n) | O(1) |
| Filtering | O(n) | O(1) |
| Transformation | O(n) | O(n) |
| Frequency | O(n) average | O(n) |

---

# Day 01 Progress

- [x] Basic traversal
- [x] Index traversal
- [x] Accumulator
- [x] Counting
- [x] Maximum
- [x] Minimum
- [x] Searching
- [x] Filtering
- [x] Transformation
- [x] Frequency counting
- [x] Most frequent element
- [x] Exactly-once elements

## Next
- [ ] Duplicate detection
- [ ] Sorting-based patterns
- [ ] Two pointers
- [ ] Sliding window
- [ ] Prefix sum
- [ ] Hashing + arrays
- [ ] Kadane's algorithm
- [ ] In-place modification
- [ ] Partitioning
- [ ] Merge-based problems
- [ ] Intervals
- [ ] 2D arrays
