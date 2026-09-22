# Questions to Search (DAA)

Q: Define state-space tree, live node, e-node, dead node in context of branch and bound.
A:
	**State-space tree**: Think of this as a tree diagram showing every possible way you can build a solution to your problem, step by step. Each node in the tree represents a partial decision (like "I've picked item 1, now deciding item 2"). The root is where you start (no decisions made), and the leaves are complete solutions.
	**Live node**: A node that has been _generated_ (created in the tree) but hasn't been fully explored yet — meaning we haven't yet looked at all of its children. It's still "alive" because there's more work to do on it.
	**E-node (Expansion node)**: This is the live node that is _currently being processed_ — the one we've picked to generate its children right now. "E" stands for "expanding." Only one node is the E-node at any given moment.
	**Dead node**: A node that is either:
		- Already fully expanded (all its children have been generated), or
		- Found to be useless — meaning it can never lead to an answer better than what we already have, so we don't bother exploring it further.

---
Q: Explain what a bounding function is, and how it helps the state-space tree.
A: 
	A **bounding function** estimates the _best possible result_ you could get if you continued down a particular branch — without actually going all the way down it.
	Why it helps: instead of blindly exploring every single branch of the tree (which takes forever), the bounding function gives you a quick "preview" or estimate. If that estimate is worse than the best solution you've already found, there's no point exploring that branch — you cut it off immediately.

---
Q: Differentiate between LIFO branch and bound, and FIFO branch and bound.
A:
	- **LIFO branch and bound:** the most recently generated live node is expanded next — uses a **stack**.
	- **FIFO branch and bound:** the earliest generated live node is expanded next — uses a **queue**.
	- LIFO dives deep quickly and uses less memory; FIFO explores level by level and generally needs more memory.

---
Q: Briefly explain how least cost branch and bound chooses the next e-node to expand.
A:
	- Live nodes are kept in a **priority queue** ordered by their **cost bound** (an estimate of the best solution reachable from that node).
	- The live node with the **smallest bound** (most promising) is selected as the next e-node.
	- This focuses the search on the branches most likely to lead to the optimal solution.

---
Q: What is pruning?
A:
	- Pruning means cutting off (removing) branches of the state-space tree that **cannot lead to a better solution** than the best one already found.
	- Such nodes become dead nodes and are never expanded further, saving both time and memory.

---