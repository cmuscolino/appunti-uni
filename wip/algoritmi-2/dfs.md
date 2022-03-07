# DFS

Visita in profondità, acronimo di Depth-First Search.

1. SI parte da un vertice
2. Scopri il primo nodo
3. Prosegui la visita finché non scopri più nodi; a quel punto torni indietro e vai nel ramo non esplorato

GOES DEEP --> VA IN PROFONDITÀ.

### Possibili utilizzi

* backtracking
* ricerca **esaustiva** di tutti i percorsi in un grafo

### Concetti fondamentali

Utilizza uno STACK -> LIFO Funziona in O(|V| + |E|) e in spazio O(|V|)

### Funzionamento

La logica è:

1. Aggiungi il nodo di partenza allo stack
2. Mentre lo stack non è vuoto
   1. prendi un nodo dallo stack
      1. se non è già stato visitato, allora aggiungilo
   2. per ogni nodo adiacente (figlio)
      1. se non è già stato visitato, allora inseriscilo nello stack

### Implementazione

```python
'''
Implement a DFS
'''

def DFS(root, seen):
	if root not in seen:
		seen.append(root)

	if root.left != None and not in seen:
		DFS(root.left, seen)

	if root.right != None and not in seen:
		DFS(root.right, seen)

'''
MAIN
'''
class Node:
	def __init__(self, key):
		self.value = key
		self.left = None
		self.right = None

root = Node(1)
root.left = Node(2)
root.right = Node(3)
root.left.left = Node(4)
root.left.right = Node(5)  

print("visita DFS:")
seen = []
DFS(root, seen)


for s in seen:
	print(s.value)
```

Approfondimenti: [video di Abdul Bari](https://www.youtube.com/watch?v=pcKY4hjDrxk) - [video di Back To Back SWE](https://www.youtube.com/watch?v=TIbUeeksXcI)
