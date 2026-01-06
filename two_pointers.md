# Two Pointers Patterns — A Complete Map

## What “Two Pointers” Really Means

Two pointers is not a single technique.
It is a **constraint-navigation strategy**: you move two indices through a structure to maintain or enforce an invariant.

Core invariant examples:

* Sum too big → shrink
* Condition violated → advance left
* Order preserved → exploit monotonicity

Usually applies to:

* Arrays
* Strings
* Linked lists

---

## 1. Opposite-End Pointers (Converging Pointers)

**Shape**

```
L → → → ← ← ← R
```

**When it works**

* Data is **sorted** or order matters
* You compare elements from both ends

**Core invariant**

* Left pointer increases value
* Right pointer decreases value

**Typical problems**

* Pair with target sum
* Palindrome checks
* Minimize/maximize something under constraint

**Examples**

* Two Sum (sorted array)
* Valid Palindrome
* Container With Most Water

**Mental rule**

> If increasing left increases value and decreasing right decreases value, you can steer toward the target.

---

## 2. Same-Direction Pointers (Fast–Slow)

**Shape**

```
slow → fast → → →
```

**When it works**

* You want to **filter**, **compress**, or **detect cycles**

**Core invariant**

* `fast` explores
* `slow` stabilizes or records valid state

**Typical problems**

* Remove duplicates
* Move zeros
* Linked list cycle detection
* Array compaction

**Examples**

* Remove Duplicates from Sorted Array
* Move Zeroes
* Floyd’s Cycle Detection

**Mental rule**

> One pointer decides *what to keep*, the other decides *where to put it*.

---

## 3. Sliding Window (Dynamic Range)

**Shape**

```
[L ........ R]
```

**When it works**

* Subarrays / substrings
* Contiguous segments
* You maintain a **window invariant**

**Core invariant**

* Window satisfies a condition
* Expand right
* Shrink left when violated

**Typical problems**

* Longest / shortest subarray
* Frequency-based constraints
* At most / at least K conditions

**Examples**

* Longest Substring Without Repeating Characters
* Max Consecutive Ones III
* Minimum Window Substring

**Mental rule**

> Never recompute the window. Adjust it.

---

## 4. Fixed-Window Two Pointers

**Shape**

```
[L ---- fixed size ---- R]
```

**When it works**

* Window size is constant
* You slide uniformly

**Core invariant**

* Window length = K

**Typical problems**

* Averages
* Fixed-length optimizations

**Examples**

* Maximum Average Subarray
* K-length bit flips

**Mental rule**

> One pointer enters, one exits. Accounting must balance.

---

## 5. Partitioning Pointers (Dutch National Flag)

**Shape**

```
[ < pivot | unknown | > pivot ]
```

**When it works**

* In-place rearrangement
* Classification problems

**Core invariant**

* Left region valid
* Middle unknown
* Right region valid

**Typical problems**

* Sort colors
* QuickSort partition
* Separate odds and evens

**Examples**

* Sort Colors (0,1,2)
* Partition Array by Pivot

**Mental rule**

> Unknown region shrinks. Known regions grow.

---

## 6. Two Pointers with Counting / Frequency

**Shape**

```
[L ... R] + freq map / array
```

**When it works**

* You need uniqueness or counts
* Characters, bits, categories

**Core invariant**

* Frequency structure matches window content

**Typical problems**

* Anagrams
* Substring permutation
* K distinct elements

**Examples**

* Find All Anagrams in a String
* Longest Substring with K Distinct Characters

**Mental rule**

> Pointer movement must be mirrored in the frequency structure.

---

## 7. Two Pointers on Multiple Arrays

**Shape**

```
A[i] →  
B[j] →
```

**When it works**

* Both arrays are sorted
* You want intersection or merge-like logic

**Core invariant**

* Smaller value advances

**Typical problems**

* Intersection of arrays
* Merge sorted arrays
* Closest pair problems

**Examples**

* Intersection of Two Sorted Arrays
* Merge Two Sorted Lists

**Mental rule**

> Only advance the pointer that blocks progress.

---

## 8. Cyclic Two Pointers

**Shape**

```
→ → → ↘
↑       ↓
← ← ← ←
```

**When it works**

* Circular structures
* Repeating sequences

**Core invariant**

* Relative speed reveals structure

**Typical problems**

* Loop detection
* Happy number
* Circular array loops

**Examples**

* Linked List Cycle
* Happy Number

**Mental rule**

> If one runner laps another, a cycle exists.

---

## 9. Bitmask + Two Pointers (Advanced)

**Shape**

```
[L ... R] + bitmask
```

**When it works**

* Small alphabets
* Presence/absence tracking

**Core invariant**

* Bitmask encodes window state

**Typical problems**

* Character uniqueness
* Fast checks without maps

**Examples**

* Longest Substring Without Repeating Characters (bitmask variant)

**Mental rule**

> Replace memory with bits when domain is small.

---

## 10. Greedy Two Pointers

**Shape**

```
decision at each pointer move
```

**When it works**

* Locally optimal move leads to global optimum

**Core invariant**

* Greedy choice is safe

**Typical problems**

* Pairing
* Resource allocation

**Examples**

* Boats to Save People
* Assign Cookies

**Mental rule**

> Pair extremes to minimize waste.

---

## Common Failure Modes

* Using two pointers on **unsorted data** without a window invariant
* Forgetting to update auxiliary state (counts, sum)
* Moving both pointers blindly
* Breaking monotonicity assumptions

---

## How to Recognize Two Pointers Instantly

Ask yourself:

* Can I discard part of the search space by moving a pointer?
* Does order help me decide direction?
* Can I maintain a condition while expanding/shrinking?

If yes — two pointers are lurking.

---

## Related Topics to Study Next

* Sliding Window vs Prefix Sum tradeoffs
* Monotonic queues (next level of window optimization)
* Greedy correctness proofs
* Amortized analysis (why pointers move O(n))
* Bitmasking + window hybrids

---
