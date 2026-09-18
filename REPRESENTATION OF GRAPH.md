# Experiment 17(d): Representation of Graph

## Aim
To write a Python program to generate a graph for a given fixed degree sequence.

---

## Algorithm

1. **Start the program**:
   - Read the degree sequence from the user input.
   - The degree sequence represents the number of edges connected to each vertex in the graph.
   
2. **Define the graph representation**:
   - Create an adjacency matrix to represent the graph. The matrix will be a square matrix where each element `mat[i][j]` is `1` if there's an edge between vertex `i` and vertex `j`, and `0` otherwise.

3. **Construct the graph**:
   - Loop through all pairs of vertices (`i`, `j`).
   - If both vertices `i` and `j` have remaining degrees greater than `0`, decrement their degree and add an edge between them in the matrix.

4. **Display the adjacency matrix**:
   - Print the adjacency matrix in a human-readable format.
   
5. **End the program**:
   - The graph is now represented by the adjacency matrix, and the program prints the matrix.

---

## Program

```

class AdjNode:
	def __init__(self, data):
		self.vertex = data
		self.next = None



class Graph:
	def __init__(self, vertices):
		self.V = vertices
		self.graph = [None] * self.V

	def add_edge(self, src, dest):
	
		node = AdjNode(dest)
		node.next = self.graph[src]
		self.graph[src] = node

	
		node = AdjNode(src)
		node.next = self.graph[dest]
		self.graph[dest] = node

	
	def print_graph(self):
		for i in range(self.V):
			print(f"Adjacency list of vertex {i}\n {i}", end="")
			temp = self.graph[i]
			while temp:
				print(f" -> {temp.vertex}", end="")
				temp = temp.next
			print(" \n")

if __name__ == "__main__":
	V = 5
	graph = Graph(V)
	graph.add_edge(0, 1)
	graph.add_edge(0, 4)
	graph.add_edge(1, 2)
	graph.add_edge(1, 3)
	graph.add_edge(1, 4)
	graph.add_edge(2, 3)
	graph.add_edge(3, 4)

	graph.print_graph()


```

## OUTPUT
![image](https://github.com/user-attachments/assets/b1572d5e-e164-48c5-930b-96e244a97621)

## RESULT
The program successfully generated and displayed the adjacency list representation of the graph for the given fixed degree sequence. Each vertex's adjacency list correctly shows all connected vertices, demonstrating proper graph construction and representation.
