# LeetCode 153 - Find Minimum in Rotated Sorted Array

## Problem Statement

Suppose an array of unique integers is sorted in ascending order and then rotated between 1 and n times.

Given the rotated sorted array `nums`, return the minimum element of the array.

You must solve it in O(log n) time, although the following solution uses a brute-force approach.

---

## Example 1

Input:
nums = [3,4,5,1,2]

Output:
1

---

## Example 2

Input:
nums = [4,5,6,7,0,1,2]

Output:
0

---

## Example 3

Input:
nums = [11,13,15,17]

Output:
11

---

## Approach (Brute Force)

1. Assume the first element is the minimum.
2. Traverse the array from the second element to the end.
3. If the current element is smaller than the current minimum, update the minimum.
4. After traversing the entire array, return the minimum value.

---

## Java Solution

```java
class Solution {
    public int findMin(int[] nums) {
        int n = nums.length;
        int min = nums[0];

        for (int i = 1; i < n; i++) {
            if (nums[i] < min) {
                min = nums[i];
            }
        }

        return min;
    }
}
```

---

## Dry Run

Input:

nums = [4,5,6,7,0,1,2]

Initial:
min = 4

| i | nums[i] | min |
|---|---------|-----|
| 1 | 5 | 4 |
| 2 | 6 | 4 |
| 3 | 7 | 4 |
| 4 | 0 | 0 |
| 5 | 1 | 0 |
| 6 | 2 | 0 |

Return:

0

---

## Complexity Analysis

### Time Complexity

- O(n)

The array is traversed once.

### Space Complexity

- O(1)

Only one extra variable (`min`) is used.

---

## Key Insight

The brute-force solution checks every element and keeps track of the smallest value encountered. While simple and easy to understand, it does not take advantage of the rotated sorted property of the array. The optimal solution uses Binary Search to achieve O(log n) time complexity.
