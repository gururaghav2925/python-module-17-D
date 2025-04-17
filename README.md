# Topological Sorting of a Directed Acyclic Graph (DAG) in Python

##  Aim
To implement a Python program that performs and prints the topological sorting of a Directed Acyclic Graph (DAG).

## Procedure
1. Represent the graph using an adjacency list.
2. Use Depth-First Search (DFS) to explore the graph.
3. After visiting all adjacent vertices of a node, push the node onto a stack.
4. Reverse the stack to get the topological ordering.

##  Code Snippet
```python
# A Python3 program to print topological sorting of a DAG
def addEdge(u, v):
	global adj
	adj[u].append(v)

# The function to do DFS() and stores departure time
# of all vertex
def DFS(v):
	global visited, departure, time
	visited[v] = 1
	for i in adj[v]:
		if visited[i] == 0:
			DFS(i)
	departure[time] = v
	time += 1

# The function to do Topological Sort. It uses DFS().
def topologicalSort():

	# perform DFS on all unvisited vertices
	for i in range(V):
		if(visited[i] == 0):
			DFS(i)

	# Print vertices in topological order
	for i in range(V - 1, -1, -1):
		print(departure[i], end = " ")

# Driver code
if __name__ == '__main__':
	# Create a graph given in the above diagram
	V,time, adj, visited, departure = 6, 0, [[] for i in range(7)], [0 for i in range(7)],[-1 for i in range(7)]
	addEdge(5, 2)
	addEdge(5, 0)
	addEdge(4, 0)
	addEdge(4, 1)
	addEdge(2, 3)
	addEdge(3, 1)

	print("Topological Sort of the given graph is")
	topologicalSort()
```

## Output:

![image](https://github.com/user-attachments/assets/1c89cbcb-fd14-406e-a3e5-02f8aaf69193)

## Result:
The program successfully prints the topological order of the nodes in the given DAG.

