# Assignment 2: Binary Search Tree vs Linear Search

**Student Name:** Yuktha Krishna
**Repository:** BST-Identification-Assignment

## 1. Trace Table (BST Insertion)
Identifications inserted in order: `A102, A25, A7, B100, B12, A120, B3, A45`

| Step | Key Inserted | Insertion Path | Resulting Position |
| :--- | :--- | :--- | :--- |
| 1 | **A102** | Root node | Root |
| 2 | **A25** | A25 > A102 | Right child of A102 |
| 3 | **A7** | A7 > A102 -> A7 > A25 | Right child of A25 |
| 4 | **B100** | B100 > A102 -> B100 > A25 -> B100 > A7 | Right child of A7 |
| 5 | **B12** | B12 > A102 -> B12 > A25 -> B12 > A7 -> B12 < B100 | Left child of B100 |
| 6 | **A120** | A120 > A102 -> A120 < A25 | Left child of A25 |
| 7 | **B3** | B3 > A102 -> ... -> B3 > B12 | Right child of B12 |
| 8 | **A45** | A45 > A102 -> ... -> A45 < A7 | Left child of A7 |

## 2. Search Performance Comparison
| Key | Linear Search Comparisons | BST Search Comparisons | Status |
| :--- | :--- | :--- | :--- |
| **A7** | 3 | 3 | Found |
| **B12** | 5 | 5 | Found |
| **A45** | 8 | 4 | Found |
| **C9** | 8 | 6 | Not Found |

## 3. Complexity & Discussion
- **Linear Search:** Time complexity is O(n) in worst/average case.
- **BST Search:** Time complexity is O(log n) average, degradation to O(n) worst-case if skewed.
- **Key Length & Order Impact:** Insertion sequence heavily influences tree height. Pre-sorting keys leads to skewed trees, increasing lookup comparisons.
- **Recommendation for Large Database:** Migrate to Self-Balancing BSTs (AVL / Red-Black Tree) or B-Trees to ensure balanced log-time lookups regardless of input insertion order.
