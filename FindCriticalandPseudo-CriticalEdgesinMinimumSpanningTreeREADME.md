# leet-day36

# Finding Critical and Pseudo-Critical Edges in Minimum Spanning Tree

This C++ solution solves the problem of finding critical and pseudo-critical edges in a given graph's minimum spanning tree (MST).

## Problem Description

Given a weighted undirected connected graph with `n` vertices numbered from 0 to `n - 1`, and an array `edges` where `edges[i] = [ai, bi, weighti]` represents a bidirectional and weighted edge between nodes `ai` and `bi`, the goal is to find all the critical and pseudo-critical edges in the graph's MST.

An MST is a subset of the graph's edges that connects all vertices without cycles and with the minimum possible total edge weight. A critical edge is an MST edge whose deletion would cause the MST weight to increase. A pseudo-critical edge can appear in some MSTs but not all.

## Approach

The provided solution implements the following approach:

1. **Union-Find Data Structure**: A `UnionFind` class is defined to manage sets of vertices and handle union and find operations efficiently.

2. **Sorting Edges**: The `edges` array is sorted based on edge weights using the `cmp` comparison function.

3. **Calculate MST Weight**: The `findMST` function calculates the weight of the MST, considering the exclusion of an edge represented by its index. This function is used to calculate the MST weight before and after excluding an edge.

4. **Find Critical and Pseudo-Critical Edges**: The solution iterates through the sorted edges. For each edge, it calculates the MST weight with and without that edge using the `findMST` function. If excluding an edge increases the MST weight, the edge is critical. If excluding an edge doesn't change the MST weight, the edge is pseudo-critical.

5. **Output**: The solution returns two vectors: one containing the indices of critical edges and another containing the indices of pseudo-critical edges.

## Usage

To use the solution, create an instance of the `Solution` class and call the `findCriticalAndPseudoCriticalEdges` function with the `n` value and the `edges` array.

```cpp
Solution solution;
int n = 5;
vector<vector<int>> edges = {{0,1,1},{1,2,1},{2,3,2},{0,3,2},{0,4,3},{3,4,3},{1,4,6}};
vector<vector<int>> result = solution.findCriticalAndPseudoCriticalEdges(n, edges);
```

## Complexity

- **Time Complexity**: The overall time complexity is dominated by the sorting of the edges, which is O(E log E), where E is the number of edges. Other parts of the solution, such as Union-Find operations and MST weight calculations, have lower time complexities.

- **Space Complexity**: The space complexity is O(n) for the Union-Find data structure and O(1) for other variables, resulting in an efficient use of memory.

## Summary

This solution employs a well-optimized approach using Union-Find and Kruskal's algorithm to efficiently find critical and pseudo-critical edges in a graph's minimum spanning tree. It balances time and space complexity to provide a practical and efficient solution for the problem.
