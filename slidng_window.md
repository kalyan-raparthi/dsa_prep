
**Why It Works**
- “At most” is monotonic
- “Exactly” is not directly monotonic

**Use Cases**
- Exactly `k` distinct elements
- Exactly `k` odd numbers

---

## 5. Sliding Window with Frequency Map / Array

**State**
- Frequency array or hash map
- Distinct count

**Use Cases**
- Anagram detection
- Permutation in string
- Character replacement problems

**Optimization**
- Small alphabet → array
- Large domain → hash map

---

## 6. Sliding Window with Lazy Statistics

**Idea**
- Maintain an upper bound statistic without decreasing it

**Example**
- Track `maxFreq` even when shrinking

**Why It Works**
- Overestimation may delay shrinking
- Never causes invalid expansion

**Use Cases**
- Longest repeating character replacement

---

## 7. Sliding Window with Monotonic Deque

**Data Structure**
- Monotonic increasing or decreasing deque

**Invariant**
- Deque stores candidates for min or max

**Operations**
- Pop back to maintain order
- Pop front when index exits window

**Use Cases**
- Sliding window maximum / minimum
- Subarrays with bounded max − min

---

## 8. Two-Pointer Sliding Window

**Invariant**
- Range-based condition, often on sorted data

**Movement**
- Either pointer may move depending on condition

**Use Cases**
- Pair sum in sorted array
- Triplet problems
- Window difference constraints

---

## 9. Sliding Window on Streams and Time Windows

**Domain**
- Strings
- Event streams
- Logs

**Invariant Examples**
- Events in last `k` seconds
- Characters in last `k` positions

---

## 10. When Sliding Window Does NOT Work

Sliding window fails when:

- Values can be negative and rely on sum monotonicity
- Invariant is non-monotonic
- You need to revisit earlier right pointers

**Example**
- Subarray sum = `k` with negative numbers  
  → Use prefix sum + hash map

---

## Decision Checklist

Ask these questions:

1. Is the condition monotonic when expanding `R`?
2. Can validity be restored by only moving `L` forward?
3. Can state be updated incrementally?

If all are **yes** → sliding window applies.

---

## Mental Model

Sliding window is **controlled memory**:
- Remember only what the current window needs
- Forget everything else efficiently

---
