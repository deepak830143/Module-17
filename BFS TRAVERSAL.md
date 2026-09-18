# Experiment 17b: BFS Traversal

## Aim
To write a Python program to print the BFS (Breadth-First Search) traversal from a given source vertex in a graph.

---

## Algorithm

1. **Start the program**:
   - Create a graph using an adjacency list representation.
   - Add edges between vertices using the `addEdge()` function.

2. **Implement the BFS function**:
   - Initialize all vertices as not visited.
   - Use a queue to track the vertices for traversal.
   - Mark the starting vertex as visited and enqueue it.
   - Dequeue a vertex, process it, and enqueue all its adjacent unvisited vertices while marking them as visited.

3. **Input**:
   - The user provides the starting vertex for the BFS traversal.

4. **Perform BFS traversal**:
   - Start from the given source vertex and traverse all reachable vertices using BFS.
   - Print the vertices in the BFS order.

5. **End the program**:
   - The program outputs the order of vertices visited during the BFS traversal.

---

## Program

```

from collections import defaultdict


class Graph:

	def __init__(self):

	
		self.graph = defaultdict(list)

	def addEdge(self,u,v):
		self.graph[u].append(v)

	def BFS(self, s):

		visited = [False] * (max(self.graph) + 1)

		queue = []

		queue.append(s)
		visited[s] = True
		while queue:

			s = queue.pop(0)
			print (s, end = " ")

			for i in self.graph[s]:
				if visited[i] == False:
					queue.append(i)
					visited[i] = True
n=int(input())
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)

print ("Following is Breadth First Traversal"
				" (starting from vertex {})".format(n))
g.BFS(n)




```

## OUTPUT

![image](https://github.com/user-attachments/assets/51c28555-eab6-411e-955f-3a7d0e6f91a4)

## RESULT
The Python program for Breadth-First Search (BFS) traversal was successfully implemented. The program accepts a starting vertex and correctly outputs the order of vertices visited using BFS, demonstrating the correct traversal of the graph.








