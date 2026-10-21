# Leetcode_Day81
# Day 81: Minimum Value to Get Positive Step by Step Sum

**LeetCode Problem:** 1413. Minimum Value to Get Positive Step by Step Sum  
**Difficulty:** Easy  
**Language:** Java  
**Topics:** Arrays, Prefix Sum

## Problem Statement

Given an integer array `nums`, find the minimum positive starting value such that the running sum never becomes less than `1`.

The running sum is calculated by adding the elements of the array to the starting value, one by one, from left to right.

Return the minimum positive starting value that keeps every running sum at least `1`.

## Approach

I used the **Prefix Sum** concept to track the running sum and find its minimum value.

1. Initialize `sum = 0` to calculate the running sum.
2. Initialize `minSum = 0` to track the minimum running sum.
3. Traverse the array and add each element to `sum`.
4. Update `minSum` whenever the running sum reaches a new minimum.
5. Return `1 - minSum` to calculate the minimum starting value needed to keep the running sum positive.

Since the starting value must be positive and every step-by-step sum must be at least `1`, this approach finds the required value in a single traversal.

## Java Solution

```java
class Solution {
    public int minStartValue(int[] nums) {
        int sum = 0;
        int minSum = 0;

        for (int num : nums) {
            sum += num;
            minSum = Math.min(minSum, sum);
        }

        return 1 - minSum;
    }
}
```

## Example

**Input:**
```text
nums = [-3, 2, -3, 4, 2]
```

**Output:**
```text
5
```

**Explanation:**

Starting with `5`, the step-by-step sums are:

- `5 + (-3) = 2`
- `2 + 2 = 4`
- `4 + (-3) = 1`
- `1 + 4 = 5`
- `5 + 2 = 7`

The running sum never becomes less than `1`, so the minimum starting value is `5`.

## Complexity Analysis

- **Time Complexity:** O(n), because the array is traversed only once.
- **Space Complexity:** O(1), because only a constant number of variables are used.

Here, `n` represents the length of the array.

## What I Learned

- How to use prefix sums to track cumulative values.
- How the minimum running sum helps determine the required starting value.
- How to solve an array problem efficiently in a single traversal.
- Why tracking the minimum value can be more useful than repeatedly testing different starting values.

## Takeaway

Sometimes, finding the right answer isn't about trying every possibility. It's about identifying the one important value that determines the result.

**Day 81 complete! One more problem solved, one more step forward in my DSA journey.**
