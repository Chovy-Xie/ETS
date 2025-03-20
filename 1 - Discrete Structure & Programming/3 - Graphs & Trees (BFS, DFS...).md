# Graphs & Trees
> BFS, DFS, Shortest Path, Spanning Trees

## Breadth-First Search (BFS)

### What is BFS

- BFS is a graph traversal algorithm that explores all neighboring nodes before moving to the next level of nodes.
- It's particularly useful for finding the shortest path in an unweighted graph and solving problems related to connectivity, cycles, and levels of a graph. 

### Key Characteristics of BFS

1. Uses a Queue (FIFO - First In, First Out)
    - BFS relies on a queue to explore nodes in a level-by-level manner
    - Nodes are processed in the order they are discovered
2. Explores All Neighbors Before Moving Deeper
    - BFS examines all adjacent nodes before going to the next level
    - This ensures that nodes are visited in order of increasing distance from the start node
3. Finds the Shortest Path in an Unweighted Graph
    - BFS guarantees the shortest path (minimum number of edges) in an unweighted graph
    - This is useful for routing problems, social network analysis, and shortest paths
4. Works for Both Trees and Graphs
    - BFS is used in both tree traversal (level-order traversal) and graph traversal
    - Unlike trees, graphs may contain cycles, so BFS must track visited nodes
5. Time Complexity: O(V + E)
    - V = Number of vertices(nodes), E = Number of edges
    - Each node is visited once, and each edge is checked once, making BFS efficient
6. Space Complexity: O(V + E) in an adjacency list representation
    - Queue Storage (O(V))
        - BFS uses a queue (FIFO) to store nodes at each level
        - In the worst case (e.g., complete binary tree), the queue can store up to V/2 nodes at the last level, which is O(V)
    - Adjacency List Storage (O(V + E))
        - The graph itself is stored as an adjacency list, which takes O(V + E) space

### How BFS Works
> BFS explores all neighboring nodes before moving to the next level, and it follows a queue-based approach (FIFO) to ensure level-order traversal.

1. Start with a source node and mark it as visited
2. Push it into a queue
3. While the queue is not empty: 
    - dequeue a node
    - visit all its unvisited neighbors
    - mark neighbors as visited and enqueue them
4. Repeat until all reachable nodes are visited

### BFS Algorithm
```
{/* Pseudocode */}
BFS(Graph, StartNode): 
    Initialize an empty queue
    Enqueue StartNode and mark it as visited

    While the queue is not empty: 
        Dequeue a node from the front
        Process the node (e.g., print it)

        For each unvisited neighbor of the node: 
            Mark it as visited
            Enqueue it
```

```
# BFS implementation in Python

from collections import deque

def bfs(graph, start): 
    visited = set()
    queue = deque([start])

    while queue: 
        node = queue.popleft()
        if node not in visited: 
            print(node, end=" ")  # process node
            visited.add(node)
            queue.extend(graph[node])  # add unvisited neighbors

# Example Graph (adjacency list representation)
graph = {  
    0: [1, 2],
    1: [0, 3, 4],
    2: [0, 5, 6],
    3: [1],
    4: [1],
    5: [2],
    6: [2]
}

print("BFS Travesal: ")
bfs(graph, 0)  # expected output: 0 1 2 3 4 5 6
```


## Depth-First Search (DFS)

### What is DFS

- DFS is a graph travesal algorithm that explores as far as possible along each branch before backtracking. 
- It uses a stack (LIFO - Last In, First Out) or recursion to traverse a graph or tree.