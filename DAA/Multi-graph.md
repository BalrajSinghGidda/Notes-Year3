---
subject: DAA
date: 2026-09-23
topics-covered:
  - Multi-stage graph definition and structure
  - Source and sink stages
  - Shortest path via dynamic programming
  - Forward and backward approaches
---

# Multi-stage Graph

## Topics covered

- Definition of a multi-stage graph
- Structure: stages, source and sink
- Shortest path between source and sink
- Dynamic programming: forward and backward approaches

## Notes

- A multi-stage graph is a directed graph in which all vertices are divided into **stages**, such that all edges are directed only from a vertex of the current stage to a vertex of the next stage — there is no edge between vertices of the same stage, nor from a later stage back to an earlier one.
- Both the first and the last stage contain only one vertex: the **source** and the **destination (sink)** respectively.
- In a multi-stage graph, we are required to find the **shortest path between the source and the sink**. This problem can be solved using **dynamic programming**, using the forward approach and the backward approach.

### Forward Approach

- Assume that there are $k$ stages in the graph.
- Start from the last stage, and find out the cost of each and every node down to the first stage.
- Find the minimum-cost path from source to destination, i.e., from stage 0 to stage $k$.

## Examples worked in class

- (To be added)

## Questions to research

- How does the backward approach differ from the forward approach, and when is each preferred?
- What is the complexity of the dynamic programming solution for a $k$-stage graph with $n$ vertices?

## See also

- [[Bellman Ford]] — all-pairs shortest path via dynamic programming
- [[Branch and Bound]] — exact optimisation on state-space trees