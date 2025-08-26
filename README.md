# Exp. No: 17a 
## Representation of Graph – Write a Python program to generate a graph for a given fixed degree sequence

###  Aim
To Write a Python program to generate a graph for a given fixed degree sequence


###  Algorithm

Start the program.

Input the fixed degree sequence from the user.

Import the required libraries (networkx and matplotlib).

Create a graph using the degree sequence.

Check if the degree sequence is valid using the Havel-Hakimi algorithm.

Generate the graph using nx.havel_hakimi_graph().

Draw the graph using matplotlib.

Display the graph.

End the program.

### 🧾 Program
```
# Python3 program to generate a graph
# for a given fixed degrees

# A function to print the adjacency matrix.
def printMat(degseq, n):
	
	# n is number of vertices
	mat = [[0] * n for i in range(n)]

	for i in range(n):
		for j in range(i + 1, n):

			# For each pair of vertex decrement
			# the degree of both vertex.
			if (degseq[i] > 0 and degseq[j] > 0):
				degseq[i] -= 1
				degseq[j] -= 1
				mat[i][j] = 1
				mat[j][i] = 1

	# Print the result in specified form
	print("      ", end ="")
	for i in range(n):
		print(" ", "(", i, ")", end ="")
	print()
	print()
	for i in range(n):
		print("  ", "(", i, ")", end = " ")
		for j in range(n):
			print("  ", mat[i][j], end = " ")
		print()

# Driver Code
degseq=[]
for i in range(0, 5):
    ele = int(input())
  
    degseq.append(ele)
#degseq =[v0,v1,v2,v3,v4]

n = len(degseq)
printMat(degseq, n)

```

### OUTPUT
<img width="798" height="289" alt="image" src="https://github.com/user-attachments/assets/bd85f737-c839-4041-bb60-5c62ab3c3189" />


### RESULT
Thus the program was executed successfully 





# Exp. No: 17b 
## Breadth First Search – Write a Python  program to print BFS traversal from a given source vertex. 



###  Aim
To Write a Python  program to print BFS traversal from a given source vertex. 



###  Algorithm

Start the program.

Input the number of vertices and edges of the graph.

Create an adjacency list to represent the graph.

Input the edges between vertices.

Input the source vertex.

Initialize a queue and a visited list to track visited vertices.

Enqueue the source vertex and mark it as visited.

Repeat until the queue is empty:

Dequeue a vertex and print it.

Enqueue all its unvisited adjacent vertices and mark them as visited.

End the program.
### 🧾 Program
```
# Python3 Program to print BFS traversal
# from a given source vertex. BFS(int s)
# traverses vertices reachable from s.
from collections import defaultdict

# This class represents a directed graph
# using adjacency list representation
class Graph:

	# Constructor
	def __init__(self):

		# default dictionary to store graph
		self.graph = defaultdict(list)

	# function to add an edge to graph
	def addEdge(self,u,v):
		self.graph[u].append(v)

	# Function to print a BFS of graph
	def BFS(self, s):

		# Mark all the vertices as not visited
		visited = [False] * (max(self.graph) + 1)

		# Create a queue for BFS
		queue = []

		# Mark the source node as
		# visited and enqueue it
		queue.append(s)
		visited[s] = True
		while queue:
		    s=queue.pop(0)
		    print(s,end=" ")
		    for i in self.graph[s]:
		        if visited[i]==False:
		            queue.append(i)
		            visited[i]=True

		# Write the Complete BFS Function 
		
		#....
		
		# Here
		
		#....
		
		
		
		

# Create a graph given in
# the above diagram
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

### OUTPUT
<img width="807" height="230" alt="image" src="https://github.com/user-attachments/assets/c401ff43-f2da-44b0-b8c9-c4aeff13eceb" />


### RESULT
Thus the program was executed successfully 





# Exp. No: 17c 
## Depth First Search – Write a Python  program to print DFS traversal from a given source vertex. 

###  Aim
To Write a Python  program to print DFS traversal from a given source vertex. 


###  Algorithm

Start

Input the graph and the source vertex.

Create a queue and a visited list.

Enqueue the source vertex and mark it as visited.

While the queue is not empty:
a. Remove a vertex from the queue and print it.
b. For each adjacent vertex:

If it is not visited:

Enqueue it.

Mark it as visited.

End

### 🧾 Program
```
# Python3 program to print DFS traversal
# from a given graph
from collections import defaultdict

# This class represents a directed graph using
# adjacency list representation


class Graph:

	# Constructor
	def __init__(self):

		# default dictionary to store graph
		self.graph = defaultdict(list)

	# function to add an edge to graph
	def addEdge(self, u, v):
		self.graph[u].append(v)

	# A function used by DFS
	def DFSUtil(self, v, visited):

		# Mark the current node as visited
		# and print it
		visited.add(v)
		print(v,end=" ")
		for neighbour in self.graph[v]:
		    if neighbour not in visited:
		        self.DFSUtil(neighbour,visited)
		#.....
		
		
		# Code here 
		
		
		
		#....
		
		
	# The function to do DFS traversal. It uses
	# recursive DFSUtil()
	def DFS(self, v):

		# Create a set to store visited vertices
		visited = set()

		# Call the recursive helper function
		# to print DFS traversal
		self.DFSUtil(v, visited)

# Driver code


# Create a graph given
# in the above diagram
n=int(input())
g = Graph()
g.addEdge(0, 1)
g.addEdge(0, 2)
g.addEdge(1, 2)
g.addEdge(2, 0)
g.addEdge(2, 3)
g.addEdge(3, 3)

print("Following is DFS from (starting from vertex {})".format(n))
g.DFS(n)




```

### OUTPUT
<img width="811" height="249" alt="image" src="https://github.com/user-attachments/assets/bbc49d08-0ef7-4ace-942a-4a50f0ac59ae" />


### RESULT
Thus the program was executed successfully 






# Exp. No: 17d 
## Topological Sort – Write a Python  program to print topological sorting of a DAG



###  Aim
To Write a Python  program to print topological sorting of a DAG



###  Algorithm

Start

Input the directed acyclic graph (DAG).

Create a visited list (all vertices marked as not visited).

Initialize an empty stack.

For each vertex in the graph:

If the vertex is not visited:

Perform DFS from that vertex:

Mark the vertex as visited

Visit all unvisited adjacent vertices recursively

After visiting all neighbors, push the vertex onto the stack

Pop all vertices from the stack one by one to get the topological order.

End

### 🧾 Program
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
    for i in range(V):
        if visited[i] == 0:
            DFS(i)
    for i in range(V-1,-1,-1):
	    print(departure[i],end=" ")

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

### OUTPUT
<img width="793" height="194" alt="image" src="https://github.com/user-attachments/assets/61763067-fb9e-4aba-985a-0a8b6ddbbc03" />



### RESULT
Thus the program was executed successfully 






# Exp. No: 17e
## SEB – Write A Python program to demonstrate the adjacencylist representation of the graph.

###  Aim
To Write A Python program to demonstrate the adjacency list representation of the graph.


###  Algorithm

Start the program.

Input the number of vertices and edges of the graph.

Create an empty adjacency list for all vertices.

Input all edges and update the adjacency list for each vertex.

Display the adjacency list.

### 🧾 Program
```
"""
A Python program to demonstrate the adjacency
list representation of the graph
"""

# A class to represent the adjacency list of the node


class AdjNode:
	def __init__(self, data):
		self.vertex = data
		self.next = None


# A class to represent a graph. A graph
# is the list of the adjacency lists.
# Size of the array will be the no. of the
# vertices "V"
class Graph:
	def __init__(self, vertices):
		self.V = vertices
		self.graph = [None] * self.V

	# Function to add an edge in an undirected graph
	def add_edge(self, src, dest):
		# Adding the node to the source node
		node = AdjNode(dest)
		node.next = self.graph[src]
		self.graph[src] = node

		# Adding the source node to the destination as
		# it is the undirected graph
		node = AdjNode(src)
		node.next = self.graph[dest]
		self.graph[dest] = node

	
	def print_graph(self):
	    for i in range(self.V):
	        print("Adjacency list of vertex {}  \n {} ".format(i,i), end="")
	        temp=self.graph[i]
	        while temp:
	            print("-> {} ".format(temp.vertex), end="")
	            temp=temp.next
	        print("\n")
		
	
# Driver program to the above graph class
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

### OUTPUT
<img width="628" height="460" alt="image" src="https://github.com/user-attachments/assets/97a63449-b4e0-4362-a77e-003d0151b211" />




### RESULT
Thus the program was executed successfully 
