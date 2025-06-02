# CPP MODULE 11 :

# 11a :

# PROGRAM STATEMENT :
Given a weighted, undirected and connected graph of V vertices and E edges. The task is to find the 
sum of weights of the edges of the Minimum Spanning

# ALGORITHM :
1. Initialize Graph: Represent the graph using an edge list or adjacency matrix with weights. 
Use a parent array to track the subsets of nodes.
2. Sort Edges: Sort all edges in ascending order of weight using a sorting algorithm or STL.
3. Apply Kruskal’s Algorithm: Iterate through the sorted edges, adding each edge to the 
Minimum Spanning Tree (MST) if it doesn’t form a cycle (use union-find to check and 
merge subsets).
4. Track MST Weight: Keep a running sum of the weights of edges included in the MST.
5. Output Result: Display the edges in the MST and the total weight of the tree..

# PROGRAM :
NAME : Vikash A R
REG NO : 212222040179
```
void Graph::addEdge(int u, int v, int w)
{
 adj[u].push_back(make_pair(v,w));
 adj[v].push_back(make_pair(u,w));
 
 }
```

# OUTPUT :
 ![image](https://github.com/user-attachments/assets/8a812fee-f427-463b-864e-d0a8890a327d)

# RESULT :
Thus, The program is verified and executed successfully.The outputs match the expected 
results, confirming its correctness.

# 11b :

# PROGRAM STATEMENT :
Construct the minimum spanning tree (MST) for the given graph using Kruskal’s Algorithm

# ALGORITHM :
1. Initialize Data Structures: Use a std::vector<int> to store the minimum cost to reach each 
city, initialized with infinity (INT_MAX), except for the source city 0 which is set to 0.
2. Use a Priority Queue (Min-Heap): Create a priority queue to store cities along with their 
accumulated flight costs, starting with city 0.
3. Dijkstra’s Algorithm: Extract the city with the minimum accumulated cost from the queue, 
and for each neighboring city, update its cost if a cheaper path is found.
4. Update Costs: Push the updated cities with their new costs into the priority queue and 
repeat until all cities are processed.
5. Return Minimum Cost: Once the destination city N-1 is reached or the queue is empty, 
return the minimum cost to reach city N-1

# PROGRAM :
```
void addEdge(int x, int y, int w)
{
 edgelist.push_back({w, x, y});
 }
```

# OUTPUT :
 ![image](https://github.com/user-attachments/assets/24e2f051-f40e-4b74-8e95-a7f3ff8eb100)

# RESULT :
Thus, The program is verified and executed successfully.The outputs match the expected 
results, confirming its correctness.

# 11c :

# PROGRAM STATEMENT :
There are n cities connected by some number of flights. You are given values indicating [fromi, toi, 
pricei] means that there is a flight from city fromi to city toi with cost pricei.
Write a CPP addEdge() function to find the Dijkstra's shortest path and to print the cheapest 
price from src to all other cities for the given graph. (Note: Source vertex is 0 always).

# ALGORITHM :
1. Graph Representation: Use an adjacency list std::vector<std::vector<pair<int, int>>> to 
store the cities and their corresponding flight costs, where each edge is represented as 
(destination, cost).
2. Dijkstra’s Initialization: Initialize a std::vector<int> to store the minimum cost to each 
city, starting with 0 for the source city (src = 0), and set all other cities' costs to infinity 
(INT_MAX).
3. Priority Queue: Use a priority queue (min-heap) to process cities starting from the source 
city, where each element in the queue is a pair (cost, city).
4. Relaxation: For each city, check its neighbors, and if a cheaper path is found, update the 
minimum cost and push the updated city and cost into the priority queue.
5. Output Results: After processing all cities, print the minimum cost to reach each city from 
the source (0). If a city is unreachable, print -1 for that city.

# PROGRAM :
```
int main()
{
int n, m;
cin >> n >> m;
Graph g(n);
for (int i = 0; i < m; i++)
{
int x, y, w;
cin >> x >> y >> w;
g.addEdge(x, y, w);
}
g.shortestPath(0);
return 0;
}
```

# OUTPUT :
 ![image](https://github.com/user-attachments/assets/2d2d490f-14dd-4058-a8b8-0fe7ce11de8f)

# RESULT :
Thus, The program is verified and executed successfully.The outputs match the expected 
results, confirming its correctness.

# 11d :

# PROGRAM STATEMENT :
Dora got a map in her hand with ‘N’ cities numbered 1 to ‘N’, connected with bridges. Bujji asks 
her to find bridge(s) in the given graph. To help Dora, fix the errors in the given CPP function to 
identify bridge(s) in a graph..

# ALGORITHM :
1. DFS Initialization: Perform a Depth First Search (DFS) on the graph, initializing arrays for 
discovery time (disc[]), the lowest point reachable (low[]), and parent tracking (parent[]).
2. DFS Traversal: During DFS traversal, for each edge (u, v), check if v is unvisited. If so, 
recursively call DFS for v, update low[u], and check if low[v] is greater than disc[u] to 
identify a bridge.
3. Backtracking: After visiting all neighbors of v, backtrack and update low[u] based on the 
discovery time of v and its neighbors.
4. Identify Bridges: If low[v] > disc[u] for an edge (u, v), mark it as a bridge since removing it 
disconnects the graph.
5. Output Bridges: After DFS traversal, print all identified bridges.

# PROGRAM :
```
void Graph::bridge()
{
bool *visited = new bool[V];
int *disc = new int[V];
int *low = new int[V];
int *parent = new int[V];

 for (int i = 0; i < V; i++)
{
parent[i] = NIL;
visited[i] = false;
}
for (int i = 0; i < V; i++)
{
 if (visited[i] == false)
 {
 bridgeUtil(i, visited, disc, low, parent);
 }
}
```

# OUTPUT :
 ![image](https://github.com/user-attachments/assets/6629bb40-c8d7-494b-affc-95c67b5ae50d)

# RESULT :
Thus, The program is verified and executed successfully.The outputs match the expected 
results, confirming its correctness.
