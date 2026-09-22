---
subject: DAA
date: 2026-09-07
topics-covered:
  - State-space tree and node types
  - Bounding function
  - FIFO, LIFO and least-cost search strategies
  - Pruning
---

# Branch and Bound

## Topics covered

- State-space tree (root, nodes, leaves)
- Live node, e-node (expansion node) and dead node
- Bounding function and pruning
- FIFO, LIFO and least-cost search strategies

## Notes

- An **exact** method for solving optimisation problems by systematically exploring a state-space tree and pruning branches that cannot improve the best solution already found.

### State-Space Tree

- A tree showing every possible way of building a solution, step by step.
- Each node represents a **partial decision** (e.g., "I've picked item 1, now deciding item 2").
- The **root** is where you start (no decisions made); the **leaves** are complete solutions.

### Node Types

- **Live node:** a node that has been generated but not fully explored — its children have not all been examined yet. It is still "alive" because there is more work to do on it.
- **E-node (Expansion node):** the live node currently being processed — the one picked to generate its children right now. "E" stands for "expanding". Only one node is the E-node at any given moment.
- **Dead node:** a node that is either:
    - Already fully expanded (all its children have been generated), or
    - Useless — it can never lead to an answer better than the best one already found, so exploring it further is pointless.

### Bounding Function

- Estimates the **best possible result** you could get if you continued down a particular branch — without actually going all the way down it.
- Why it helps: instead of blindly exploring every branch (which takes forever), the bounding function gives a quick "preview". If the estimate is worse than the best solution already found, the branch is cut off immediately.

### Search Strategies

- **FIFO branch and bound:** the earliest generated live node is expanded next — uses a **queue**. Explores level by level; generally needs more memory.
- **LIFO branch and bound:** the most recently generated live node is expanded next — uses a **stack**. Dives deep quickly and uses less memory.
- **Least-cost branch and bound:** live nodes are kept in a **priority queue** ordered by their **cost bound**. The node with the smallest bound (most promising) becomes the next e-node, focusing the search on branches most likely to contain the optimal solution.

### Pruning

- Cutting off (removing) branches of the state-space tree that **cannot lead to a better solution** than the best one already found.
- Such nodes become dead nodes and are never expanded further — saving time and memory.

## Examples worked in class

- The Travelling Salesman Problem (see [[Travelling Salesman Problem]]) is a classic optimisation problem solved using branch and bound.

## Questions to research

- Define state-space tree, live node, e-node, dead node in the context of branch and bound.
- Explain what a bounding function is and how it helps prune the state-space tree.
- Differentiate between LIFO, FIFO, and least-cost branch and bound search strategies.
- Describe how least-cost branch and bound selects the next e-node to expand using a priority queue.
- What is pruning in branch and bound, and why does it save time and memory?

## See also

- [[Travelling Salesman Problem]] — an optimisation problem solvable with branch and bound