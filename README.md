# Leaky Forcing Number Algorithm

### Overview
This repository contains a SageMath-based implementation for computing leaky forcing sets and the leaky forcing number of a graph for both standard zero forcing and positive semidefinite zero forcing. The provided algorithms are designed to identify forts in the graph and determine the minimal forcing set intersecting all such forts for a specified number of leaks where, for a given graph, a fort is a subset of vertices for which, coloring all other vertices outside the blue, no other forces can take place under the specified forcing rule. This implementation was motivated by [1] and [2]. 

### The code defines two main functions:

#### LeakyForts(graph, leaks, PSD): Computes and returns a list of forts for a specified number of leaks and for a specified zero forcing rule (standard or positive semidefinte).
Parameters:
- graph: A SageMath graph object.
- leaks: Number of allowed leaks in the graph.
- PSD: Boolean flag; when True the function processes each connected component separately (PSD leaky forcing).
- Returns a list of vertex subsets identified as forts.

#### LeakyNumber(graph, list_of_forts, leaks, Zflist, PSDforcing, k): Calculates the minimal forcing set size by checking sets that intersect every fort in the provided collection of forts.
Parameters:
- graph: A SageMath graph object.
- list_of_forts: A list of forts.
- leaks: Number of allowed leaks in the graph.
- Zflist: Boolean flag; when True, prints all forcing sets that are found.
- PSDforcing: Boolean flag indicating whether PSD forcing is used.
- k: Candidate forcing sets size restriction; if greater than 0, only forcing sets of size exactly k are considered. If 0 or None, the search proceeds by increasing subset size. This is meant to as a possible strategy to reduce the run time. 
- Returns: The size of a minimal forcing set if found; otherwise, returns 0 if no forcing set is found.

Citation:

[1] Alameda, J. S., Dillman, S., and Kenter, F. Leaky forcing: a new variation of zero forcing.
AUSTRALASIAN JOURNAL OF COMBINATORICS 88, 3 (2024), 308–326.

[2] Olivia Elias, Ian Farish, Emrys King, Josh Kyei, and Ryan Moruzzi Jr. Leaky positive semidefinite forcing on graphs. Involve: A Journal of Mathematics, To appear.
