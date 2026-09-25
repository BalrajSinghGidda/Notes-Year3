---
subject: DAA
date: 2026-09-23
topics-covered:
  - All-pairs shortest path problem
  - Dynamic programming over a sequence of decisions
  - Matrix update formula $A^k[i,j]$
  - Worked example: $A_0 \to A_1 \to A_2$
---

# Bellman Ford

## Topics covered

- The all-pairs shortest path problem
- Dynamic programming vs. greedy for this problem
- Matrix-based updates using node $k$ as intermediate
- Worked example: $A_0$, $A_1$, $A_2$

## Notes

- It is an **all-pairs shortest path** problem.
- Works in both directed and undirected weighted graphs, but does not work with negative-weight edges.
- This problem can be solved using a greedy algorithm, but we use **dynamic programming**, because the problem can be solved by taking a sequence of decisions — also termed the **principle of optimality**.
- For self-loops, use $0$; for no edge, use $\infty$.

### Update Formula

- $A^k[i,j] = \min\{ A^{k-1}[i,j],\ A^{k-1}[i,k] + A^{k-1}[k,j] \}$

## Examples worked in class

### Matrix $A_0$ (direct distances)

|     | 1   | 2        | 3        | 4        |
| --- | --- | -------- | -------- | -------- |
| 1   | 0   | 3        | $\infty$ | 7        |
| 2   | 8   | 0        | 2        | $\infty$ |
| 3   | 5   | $\infty$ | 0        | 1        |
| 4   | 2   | $\infty$ | $\infty$ | 0        |

### Matrix $A_1$ (vertex 1 as intermediate)

- Check $A_0[2,3]$ against $A_0[2,1] + A_0[1,3]$: $2 < 8 + \infty$ — keep the direct edge, so the path via 1 is still $\infty$.

|     | 1   | 2   | 3        | 4   |
| --- | --- | --- | -------- | --- |
| 1   | 0   | 3   | $\infty$ | 7   |
| 2   | 8   | 0   | ?        | ?   |
| 3   | 5   | ?   | 0        | ?   |
| 4   | 2   | ?   | ?        | 0   |

- Filled in:

|     | 1   | 2   | 3        | 4   |
| --- | --- | --- | -------- | --- |
| 1   | 0   | 3   | $\infty$ | 7   |
| 2   | 8   | 0   | 2        | 15  |
| 3   | 5   | 8   | 0        | 1   |
| 4   | 2   | 5   | $\infty$ | 0   |

### Matrix $A_2$ (vertex 2 as intermediate)

|     | 1   | 2   | 3   | 4   |
| --- | --- | --- | --- | --- |
| 1   | 0   | 3   | ?   | ?   |
| 2   | 8   | 0   | 2   | 15  |
| 3   | ?   | 8   | 0   | ?   |
| 4   | ?   | 5   | ?   | 0   |

- Filled in:

|     | 1   | 2   | 3   | 4   |
| --- | --- | --- | --- | --- |
| 1   | 0   | 3   |     | ?   |
| 2   | 8   | 0   | 2   | 15  |
| 3   | ?   | 8   | 0   | ?   |
| 4   | ?   | 5   | ?   | 0   |

## Questions to research

- What does the running time of this algorithm depend on, and when is dynamic programming preferred over a greedy approach for shortest paths?
- Why does the algorithm fail for negative-weight edges (negative cycles)?

## See also

- [[Branch and Bound]] — another exact optimisation method
- [[Travelling Salesman Problem]] — greedy nearest-neighbour approach for a related graph problem