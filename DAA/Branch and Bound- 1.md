---
subject: ML | DAA
date: {{date}}
topics-covered:
  - 
---

# Branch And Bound
Untitled
## Topics covered

- Branch and bound

## Notes

### Branch and bound

- Branching: Main problem divides into smaller sub-problems forming a tree like structure, where each node represents a partial solution.
- Bounding: for each node, an algorithm calculates an upper bound and a lower bound on the best possible solution within the sub-problem
- Pruning: By eliminating branches that cannot yield better solutions, then the current best, the algorithm produces the number of computations, enhancing efficiency.

> Branch and bound is used in the speed optimization problem.

There are 2 types of branch and bound:
- Fixed size
- Variable size

### Classification of branch and bound problems
- FIFO branch and bound:
	- FIFO is an approach to the branch and bound problem that uses queue approach to create a state-space tree.
	- In FIFO branch and bound, the BFS is found, ie: the elements at a certain level are searched, then the elements at the next level are searched, etc, starting at the first child node at the previous level.

- LIFO branch and bound:
	- LIFO branch and bound uses stack approach in creating a state-space tree.
	- When the nodes are added to the space-state tree, they are added to the stack.
	- After all nodes are added, we pop the top-most and explore it.

- Least-count branch and bound:
	- This method uses cost-function.
	- Both LIFO and FIFO can use the least cost.
	- In this technique, the nodes are explored based on the cost of each node.
	- In this method, we explore the node which has the least node

## Examples worked in class

- ![[Pasted image 20260918155647.png]]
- N = 7
- V = N-1 = 7-1 = 6
###### Passes
- Connections: (1,2), (1,3), (1,4); (2,5); (3,2), (3,5); (4,3), (4,6); (5,7); (6,7)
- Pass 1: Take 1 as path 0 and others to $\infty$, and then explore based on the diagram (weighted)

|     | 1   | 2   | 3   | 4   | 5   | 6   | 7   |
| --- | --- | --- | --- | --- | --- | --- | --- |
| 1   | --  | 6   | 5   | 5   | --  | --  | --  |
| 2   | --  | --  | --  | --  | 5   | --  | --  |
| 3   | --  | 3   | --  | --  | 5   | --  | --  |
| 4   | --  | --  | 3   | --  | --  | 4   | --  |
| 5   | --  | --  | --  | --  | --  | --  |     |
| 6   | --  | --  | --  | --  | --  | --  | 7   |
| 7   | --  | --  | --  | --  | --  | --  | --  |
	![[Pasted image 20260918155721.png]]
## Questions to research

- Classification of branch and bound problems

## See also

