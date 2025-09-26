# Graphs 

- **Graph** $G = (V, E)$
	- $V$: set of nodes (vertices)
	- $E$: set of pairs of nodes (edges) 
		- **edge**: "line" that connects two nodes in a graph 
	- Notation: 
		- $n = |V|$ ($n$ = number of vertices in the graph)
		- $m = |E|$ ($n$ = number of edges in the graph) 


- **Edge** $e = \{u, v \}$ (also written as $e = (u, v)$
	- edge $e$ connects the two vertices $u$ and $v$ 
	- $u$ and $v$ are neighbors (next to each other in the graph)
	-  edge $e$ is **incident** to $u$ and $v$ ($e$ touches $u$ and $v$) 

- A **path** in graph $G = (V, E)$ is a sequence of vertices $P = v_1, v_2, v_3, ..., v_k$ such that: 
	- each consecutive pair $(v_i, v_{i+1})$ is connected by an edge in $E$
	- length of the path is $k - 1$ (number of edges it uses) 
	- **simple path**: path in which all vertices are distinct (now vertex appears more than once)
		- Formally: $P = v_1, v_2, ..., v_k$ with $v_i \neq v_j$ for all $i \neq j$


- A **cycle** is a path that starts and ends at the same vertex: $C = v_1, v_2, ..., v_k-1, v_k$ with $v_1 = v_k$ 
	- A **simple cycle** additionally satisfies: 
		- The first $k-1$ vertices are all distinct: $v_i \neq v_j$ for $i, j < k, i \neq j$
		- All edges are distinct 
			- so $k > 3$ (so it is not just a single edge going back and forth) 
	
- **distance** between two vertices $u$ and $v$ is the minimum number of edges in any path that connects $u$ to $v$
	- if no path exists, the distance is defined is $\infty$

- **connected graph**: graph in which there is a path between every pair of vertices (i.e. starting from any vertex, you can reach every other vertex by following edges) 

- **connected component**: 
	- definition: 
		- a *maximal subset of vertices* such that: 
			- there is a path between every pair of vertices in the subset 
			- **maximal**: you cannot add any over vertex from the graph to this subset without breaking the property that all vertices are connected to each other 
	- to find the connected components of graph $G = (V, E)$: 
		- split it's vertices into groups so that: 
			- within each group, each vertex can reach every other vertex via some other path 
			- there are no edges between vertices in different groups
		- so every group is a connected component 
	- properties: 
		- if the graph is connected, then the entire graph is just one connected component 
		- if the graph is disconnected, it has two or more connected components ("disjoint pieces" of the graph)
		- every vertex belongs to exactly one connected component
	- example: 
		- connected component 1: $\{A, B, C, D, G\}$ 
		- connected component 2: $\{E, F\}$
		- connected component 3: $\{H\}$
	

```mermaid
graph LR
    %% Component 1
    A --- B
    B --- C
    A --- D
    B --- G

    %% Component 2
    E --- F

    %% Component 3
    H
   ```

- **tree**: a connected graph with no cycles 
	- **rooted tree**: tree with parent-child relationship 
		- pick 

```mermaid
graph TB
    1 --- 4
    2 --- 4
    3 --- 4
    4 --- 5
    5 --- 6
```
