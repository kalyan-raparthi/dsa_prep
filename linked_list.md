# Linked List Patterns — Practice Map

## 1. Pointer Movement Patterns
Core idea: relative pointer positions.

### Easy
- LeetCode 876 — Middle of the Linked List  
- LeetCode 1290 — Convert Binary Number in a Linked List to Integer

### Medium
- LeetCode 19 — Remove Nth Node From End of List  
- LeetCode 83 — Remove Duplicates from Sorted List (pointer drift awareness)

---

## 2. Structural Transformation Patterns
Core idea: rewire `next`, never lose the chain.

### Easy
- LeetCode 206 — Reverse Linked List  
- LeetCode 203 — Remove Linked List Elements

### Medium
- LeetCode 92 — Reverse Linked List II  
- LeetCode 24 — Swap Nodes in Pairs

---

## 3. Detection Patterns
Core idea: cycles, convergence, and distance math.

### Easy
- LeetCode 141 — Linked List Cycle  
- LeetCode 160 — Intersection of Two Linked Lists

### Medium
- LeetCode 142 — Linked List Cycle II  
- LeetCode 234 — Palindrome Linked List

---

## 4. Window & Group Patterns
Core idea: process fixed-size chunks without indexes.

### Easy
- LeetCode 21 — Merge Two Sorted Lists  
- LeetCode 328 — Odd Even Linked List

### Medium
- LeetCode 25 — Reverse Nodes in k-Group  
- LeetCode 143 — Reorder List

---

## 5. Deletion & Filtering Patterns
Core idea: dummy nodes eliminate edge cases.

### Easy
- LeetCode 237 — Delete Node in a Linked List  
- LeetCode 83 — Remove Duplicates from Sorted List

### Medium
- LeetCode 82 — Remove Duplicates from Sorted List II  
- LeetCode 203 — Remove Linked List Elements (multi-delete)

---

## 6. Recursive Patterns
Core idea: solve from tail, rewire on unwind.

### Easy
- LeetCode 206 — Reverse Linked List (recursive version)  
- LeetCode 21 — Merge Two Sorted Lists (recursive)

### Medium
- LeetCode 24 — Swap Nodes in Pairs (recursive)  
- LeetCode 25 — Reverse Nodes in k-Group (recursive)

---

## 7. Hybrid Patterns
Core idea: when pointers alone are insufficient.

### Easy
- LeetCode 141 — Linked List Cycle (HashSet version)  
- LeetCode 160 — Intersection (length alignment)

### Medium
- LeetCode 23 — Merge k Sorted Lists  
- LeetCode 148 — Sort List

---

## Study Order (Recommended)
1. Pointer Movement  
2. Deletion & Dummy Nodes  
3. Structural Transformations  
4. Detection (cycle & intersection)  
5. Group / Window logic  
6. Recursion  
7. Hybrids

---

## Deeper Directions
- Floyd’s algorithm proof (why meeting guarantees a cycle)
- Invariants in pointer algorithms
- Persistent vs mutable linked lists
- Why linked lists perform poorly on modern CPUs
- Skip lists as a probabilistic evolution
