---

# Sliding Window Technique — Complete Reference

## 1. Definition

The **sliding window technique** is an algorithmic method used to process **contiguous segments** of linear data structures (arrays, strings, streams) by maintaining a moving range—called a *window*—that advances incrementally across the data.

The defining property is that **elements enter and leave the window in a controlled, monotonic manner**, allowing computations to be updated incrementally rather than recomputed.

---

## 2. Core Properties

* Data structure: array, string, list, or stream
* Window type: contiguous
* Pointer movement: forward-only
* Time complexity: typically `O(n)`
* Space complexity: depends on window state
* Fundamental requirement: **monotonic validity of constraints**

---

## 3. Window Representation

A window is defined by two indices:

* `left (l)` → start of window
* `right (r)` → end of window

The window represents `[l, r]` inclusive.

---

## 4. Sliding Window State

The **state** is the minimal information required to describe the current window.

Common state components:

* Sum
* Count
* Frequency map
* Distinct element count
* Maximum / minimum
* Bitmask
* Constraint violation counter

Efficient sliding window algorithms minimize state size.

---

## 5. Classification of Sliding Window Techniques

### 5.1 Fixed-Size Sliding Window

The window size `k` is constant.

Characteristics:

* Window expands by 1 and shrinks by 1 at each step
* No conditional shrinking
* Predictable movement

Typical operations:

* Rolling sum
* Rolling average
* Fixed-window frequency
* Sliding window maximum/minimum

Applications:

* Time-series smoothing
* Moving averages
* Sensor data analysis

---

### 5.2 Variable-Size Sliding Window

Window size changes dynamically based on constraints.

Core idea:

* Expand right pointer
* Shrink left pointer until invariant is restored

Used when:

* Valid window length is unknown
* Constraint-based problems

---

### 5.3 Constraint-Based Sliding Window

Window validity depends on a condition.

Examples of constraints:

* At most `k` distinct elements
* Sum ≤ `S`
* At most `k` zeros
* Frequency of any element ≤ `k`

Invariant:

> The window always satisfies the constraint.

---

### 5.4 Optimization Windows

Used to compute:

* Longest valid window
* Shortest valid window
* Maximum or minimum value under constraints

Answer updates:

* During expansion (longest)
* During shrink phase (shortest)

---

## 6. Frequency-Based Sliding Windows

State is a frequency table.

Representations:

* Fixed-size array (small alphabet)
* Hash map (large alphabet)

Key operations:

* Increment frequency on expansion
* Decrement frequency on shrink
* Track violations efficiently

Common problems:

* Anagram detection
* Permutation checking
* Substring coverage
* Pattern matching

---

## 7. “At Most K” Sliding Window Pattern

A fundamental pattern where windows track **at most K occurrences** of something.

Examples:

* At most K distinct elements
* At most K zeros
* At most K odd numbers

Property:

* The number of valid subarrays ending at `r` is `(r - l + 1)`

---

## 8. Exactly-K via At-Most Transformation

Exact-count problems are reduced using subtraction:

```
exactly K = atMost(K) − atMost(K−1)
```

Used in:

* Subarrays with exactly K distinct elements
* Binary subarrays with exact sum
* Exact parity windows

This is a higher-order sliding window technique.

---

## 9. Monotonic Queue Sliding Window

Used for range queries inside a window.

Data structure:

* Deque (double-ended queue)

Types:

* Monotonic increasing
* Monotonic decreasing

Properties:

* Front always contains optimal value
* Elements removed lazily when out of window

Supports:

* O(1) window maximum
* O(1) window minimum

---

## 10. Sliding Window with Prefix Transformations

Sometimes sliding window is applied **after transforming data**.

Transformations:

* Prefix sums
* Prefix XOR
* Difference arrays

Used when:

* Raw window is not monotonic
* Constraints become linear after transform

---

## 11. Bitmask-Based Sliding Window

State encoded using bits.

Applications:

* Small alphabet problems
* Parity tracking
* Character presence
* Palindrome feasibility checks

Advantages:

* Faster operations
* Lower memory overhead

Limitations:

* Limited expressiveness
* Fixed domain size

---

## 12. Multiple / Coupled Sliding Windows

Advanced patterns using:

* Two windows
* Nested windows
* Window + global pointer

Used when:

* One window maintains constraint
* Another tracks optimization metric

---

## 13. Circular Sliding Window

Window wraps around array end.

Techniques:

* Modulo indexing
* Array duplication
* Logical circular indexing

Applications:

* Ring buffers
* Scheduling cycles
* Circular queues

---

## 14. Sliding Window on Streams

Streaming constraints:

* No random access
* No rewind
* Bounded memory

Window types:

* Count-based
* Time-based
* Event-based

Used in:

* Real-time analytics
* Monitoring systems
* Online ML pipelines

---

## 15. Sliding Window in Systems and ML

Real-world usage:

* Time-series feature extraction
* Online statistics (mean, variance)
* Log aggregation
* Rate limiting
* Network traffic analysis
* Windowed joins in databases

---

## 16. Correctness Conditions

Sliding window is valid only if:

* Constraint satisfaction is monotonic
* Removing elements can restore validity
* No backward dependency exists

---

## 17. Common Errors

* Shrinking window only once instead of until valid
* Updating answer in wrong phase
* Tracking redundant state
* Applying sliding window where monotonicity fails
* Confusing subarrays with subsequences

---

## 18. When Sliding Window Does Not Apply

* Non-contiguous selections
* Global rearrangement problems
* Non-monotonic constraints
* Backtracking or permutation problems

---

## 19. Complexity Guarantees

* Time: `O(n)` (amortized)
* Space: `O(1)` to `O(k)`
* Each element enters and exits window once

---

## 20. Advanced Study Directions

* Formal amortized analysis
* Window algorithms in databases
* Sliding windows in distributed systems
* Hybrid window + segment tree designs
* Streaming algorithm theory
* Cache-aware window implementations

---
