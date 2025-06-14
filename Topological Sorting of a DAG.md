# Ex. No: 17D - Topological Sorting of a DAG

## AIM:
To write a Python program to **print topological sorting** of a **Directed Acyclic Graph (DAG)**.

## ALGORITHM:

**Step 1**: Create a graph and add edges to represent relationships between nodes.

**Step 2**: Use a `visited` set to keep track of visited nodes and a **stack** (or list) to record the **order of nodes** after processing.

**Step 3**: Perform **DFS** for each unvisited node:
- Explore all its neighbors.
- Recursively apply DFS to each unvisited adjacent node.
- After all neighbors are visited, **push the current node onto the stack**.

**Step 4**: After DFS is complete for all nodes, the stack will contain nodes in **reverse order of their completion time**.

**Step 5**: Print the stack in **reverse** to get the **topological order**.

---

## PYTHON PROGRAM

```
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
#.....


#Code Here


#.....





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

## OUTPUT


![image](https://github.com/user-attachments/assets/20f23428-1547-4559-bfaf-2ec1b05cb42f)



## RESULT

Thus the python program was written and executed successfully.
