# Description

Sun Devils Zero-Out Challenge

# Problem Statement

At Arizona State University, the HackerDevils club is managing a big coding event. You’re given an array of student stress levels after a long week of classes and exams. Each element in the array `nums` represents how much stress a student currently has. Through a series of club activities (queries), your job is to bring everyone’s stress down to zero.

Each query is in the form `[li, ri]`, representing a range of students from index `li` to `ri`. For a query, you may choose any subset of indices within `[li, ri]` and decrement the value at each chosen index by exactly 1.

Determine whether it is possible to make all values in `nums` equal to 0 after applying all queries in order. Return `true` if possible, otherwise return `false`.

# Input Format

- The first line contains an integer `n`, the length of `nums`.
- The second line contains `n` space-separated non-negative integers representing stress levels `nums[i]`.
- The third line contains an integer `q`, the number of queries.
- The next `q` lines each contain two integers `li ri` (0-indexed, inclusive), representing a query range.

# Constraints

- `1 \u2264 n \u2264 2 * 10^5`
- `0 \u2264 nums[i] \u2264 10^9`
- `1 \u2264 q \u2264 2 * 10^5`
- `0 \u2264 li \u2264 ri < n`
- Each query can decrement any index in its range at most once; values cannot go below 0.

# Output Format

- Return a single boolean: `true` if a zero array is achievable; otherwise `false`.

```
Sample Input 0

3
1 0 1
1
0 2

Sample Output 0

true

Explanation 0

For the only query [0, 2], choose indices 0 and 2. After decrement: [0, 0, 0].
```

```
Sample Input 1

4
4 3 2 1
2
1 3
0 2

Sample Output 1

false

Explanation 1

Query 1 [1, 3]: choose 1, 2, 3 → [4, 2, 1, 0]
Query 2 [0, 2]: choose 0, 1, 2 → [3, 1, 0, 0] (not all zeros)
```
