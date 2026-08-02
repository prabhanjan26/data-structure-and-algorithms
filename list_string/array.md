# Arrays in C++

> Last Updated: 2026-08-02

---

# Table of Contents

1. Headers
2. What is an Array?
3. Static Array vs Vector
4. Initialization
5. Input & Output
6. Traversal
7. STL Functions
8. Time Complexity
9. Common Patterns
10. Prefix Sum
11. Sliding Window
12. Two Pointers
13. Binary Search
14. Sorting
15. Hashing
16. Kadane's Algorithm
17. Monotonic Stack
18. Difference Array
19. Coordinate Compression
20. Common Interview Questions
21. Common Mistakes
22. Tips

---

# Headers

```cpp
#include <iostream>
#include <vector>
#include <algorithm>
#include <numeric>
#include <climits>
#include <unordered_map>
#include <unordered_set>
#include <set>
#include <map>

using namespace std;
```

---

# What is an Array?

An array stores elements of the same datatype in contiguous memory.

Example

```cpp
int arr[5] = {1,2,3,4,5};
```

Dynamic array

```cpp
vector<int> nums = {1,2,3,4};
```

---

# Static Array vs Vector

| Feature | Array | Vector |
|----------|------|--------|
| Size | Fixed | Dynamic |
| Resize | No | Yes |
| STL Support | Minimal | Excellent |
| Preferred | Rarely | Almost Always |

---

# Initialization

```cpp
int arr[5];

int arr[5]={1,2,3};

int arr[]={1,2,3,4};

vector<int> nums(5);

vector<int> nums(5,10);

vector<int> nums={1,2,3};
```

---

# Input

```cpp
int n;
cin>>n;

vector<int> nums(n);

for(int i=0;i<n;i++)
    cin>>nums[i];
```

---

# Output

```cpp
for(int x:nums)
    cout<<x<<" ";
```

---

# Traversal

```cpp
for(int i=0;i<n;i++)

for(auto x:nums)

for(auto &x:nums)
```

---

# Useful STL Functions

## Sort

```cpp
sort(nums.begin(),nums.end());
```

Descending

```cpp
sort(nums.rbegin(),nums.rend());
```

---

## Reverse

```cpp
reverse(nums.begin(),nums.end());
```

---

## Maximum

```cpp
int mx=*max_element(nums.begin(),nums.end());
```

---

## Minimum

```cpp
int mn=*min_element(nums.begin(),nums.end());
```

---

## Sum

```cpp
int sum=accumulate(nums.begin(),nums.end(),0);
```

---

## Count

```cpp
count(nums.begin(),nums.end(),5);
```

---

## Find

```cpp
auto it=find(nums.begin(),nums.end(),7);
```

---

## Binary Search

```cpp
binary_search(nums.begin(),nums.end(),10);
```

---

## Lower Bound

```cpp
lower_bound(nums.begin(),nums.end(),x);
```

---

## Upper Bound

```cpp
upper_bound(nums.begin(),nums.end(),x);
```

---

# Time Complexity

| Operation | Complexity |
|------------|-----------|
| Access | O(1) |
| Search | O(n) |
| Insert End (Vector) | O(1) Amortized |
| Insert Beginning | O(n) |
| Delete | O(n) |
| Sort | O(n log n) |

---

# Common Patterns

---

## 1. Linear Scan

Use when searching or checking every element.

Example

- Largest Element
- Second Largest
- Check Sorted

---

## 2. Two Pointers

Usually used on sorted arrays.

Example

```cpp
int left=0;
int right=n-1;

while(left<right)
{
}
```

Questions

- Two Sum
- Remove Duplicates
- Container With Most Water
- Squares of Sorted Array

---

## 3. Sliding Window

For contiguous subarrays.

```cpp
int left=0;

for(int right=0;right<n;right++)
{
}
```

Questions

- Maximum Sum Subarray
- Longest Substring
- Fruits Into Basket
- Max Consecutive Ones

---

## 4. Prefix Sum

```cpp
prefix[i]=prefix[i-1]+arr[i];
```

Range Sum

```
L...R

prefix[R]-prefix[L-1]
```

Questions

- Range Sum Query
- Subarray Sum Equals K

---

## 5. Binary Search

Requirements

- Sorted array

Questions

- Search Insert Position
- First Bad Version
- Peak Element

---

## 6. Hashing

```cpp
unordered_map<int,int> mp;
```

Questions

- Two Sum
- Majority Element
- Contains Duplicate

---

## 7. Kadane's Algorithm

Maximum Subarray

```cpp
current=max(arr[i],current+arr[i]);

answer=max(answer,current);
```

Questions

- Maximum Subarray
- Circular Subarray

---

## 8. Sorting

Often simplifies the problem.

Questions

- Merge Intervals
- Meeting Rooms
- 3Sum
- 4Sum

---

## 9. Monotonic Stack

Maintains increasing/decreasing order.

Questions

- Next Greater Element
- Daily Temperatures
- Largest Rectangle Histogram

---

## 10. Difference Array

Useful for range updates.

```
diff[l]+=x

diff[r+1]-=x
```

---

## 11. Coordinate Compression

When numbers are huge.

Example

```
1
100000000
500000000
```

Compress to

```
0
1
2
```

---

# Most Common Interview Questions

## Easy

- Find Maximum
- Find Minimum
- Second Largest
- Check Sorted
- Remove Duplicates
- Move Zeroes
- Rotate Array
- Missing Number
- Single Number
- Best Time to Buy Stock
- Contains Duplicate

---

## Medium

- Two Sum
- Three Sum
- Product Except Self
- Maximum Subarray
- Merge Intervals
- Set Matrix Zeroes
- Spiral Matrix
- Rotate Image
- Subarray Sum Equals K
- Maximum Product Subarray
- Majority Element II
- Sort Colors

---

## Hard

- First Missing Positive
- Trapping Rain Water
- Median of Two Sorted Arrays
- Sliding Window Maximum

---

# Common Mistakes

❌ Forgetting array bounds

```cpp
arr[n]
```

Should be

```cpp
arr[n-1]
```

---

❌ Integer Overflow

```cpp
long long sum=0;
```

---

❌ Binary Search Overflow

Wrong

```cpp
mid=(low+high)/2;
```

Correct

```cpp
mid=low+(high-low)/2;
```

---

❌ Using vector[index] without checking size

---

❌ Forgetting sorting before binary search

---

# Interview Tips

Whenever you see...

### Pair

→ Two Pointers / Hash Map

---

### Contiguous

→ Sliding Window

---

### Range Sum

→ Prefix Sum

---

### Maximum Sum

→ Kadane

---

### Sorted Array

→ Binary Search

---

### Frequency

→ Hash Map

---

### Next Greater

→ Monotonic Stack

---

### Range Update

→ Difference Array

---

# Revision Checklist

- [ ] Traversal
- [ ] STL Functions
- [ ] Prefix Sum
- [ ] Sliding Window
- [ ] Two Pointers
- [ ] Binary Search
- [ ] Hashing
- [ ] Kadane
- [ ] Sorting
- [ ] Monotonic Stack
- [ ] Difference Array
- [ ] Coordinate Compression

---

# Must Know LeetCode Problems

| Problem | Pattern |
|----------|---------|
| Two Sum | Hash Map |
| Best Time to Buy Stock | Linear Scan |
| Maximum Subarray | Kadane |
| Contains Duplicate | Hashing |
| Product Except Self | Prefix |
| Move Zeroes | Two Pointers |
| Rotate Array | Simulation |
| Merge Intervals | Sorting |
| Trapping Rain Water | Two Pointers |
| Sliding Window Maximum | Monotonic Queue |

---

# Big Picture

When solving an array problem, ask yourself:

1. Is the array sorted?
2. Do I need pairs? → Two Pointers / Hashing
3. Is it a contiguous subarray? → Sliding Window
4. Is it asking for a range? → Prefix Sum
5. Is it asking for a maximum sum? → Kadane
6. Are frequencies important? → Hash Map
7. Is binary search applicable?
8. Can sorting simplify the problem?

> **Rule of thumb:** Most array interview questions boil down to mastering **Linear Scan, Two Pointers, Sliding Window, Prefix Sum, Binary Search, Hashing, Sorting, and Kadane's Algorithm**. If you're comfortable with these patterns, you'll solve the majority of array problems asked in coding interviews.