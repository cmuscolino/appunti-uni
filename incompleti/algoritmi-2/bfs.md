# BFS

## BFS

### Cos'è

La classica visita in ampiezza (o per livello).

1. SI parte da un vertice
2. Scopri i vicini
3. Prosegui la visita nei vertici scoperti

GOES WIDE --> VA A LIVELLI

### Possibili utilizzi

Permette di trovare:

* se un path esiste tra due nodi
* cammini minimi
* componenti connesse
* alberi di visita

### Concetti fondamentali

Utilizza una CODA -> FIFO Funziona in O(|V| + |E|) e in spazio O(|V|)

### Funzionamento

La logica è:

1. aggiungo alla coda il nodo iniziale
2. mentre la coda non è vuota, prendo il primo nodo dalla coda
3. se l'array dei nodi visitati non contiene il nodo preso poco fa, allora lo aggiungiamo alla lista dei nodi visitati
4. per ogni nodo collegato al nodo di prima, se il nodo collegato non è già nella vista dei visitati mettilo in coda --> torna al punto 2
5. alla fine, nell'array dei visitati, avrò la mia visita in ampiezza

### Implementazione

```python
'''
Implement a BFS
'''

def BFS(seen, queue):
	while(len(queue) != 0):
	node_to_analyze = queue[-1]
	queue.remove(node_to_analyze)
	
	if node_to_analyze not in seen:
		seen.append(node_to_analyze)

	if node_to_analyze.left != None and node_to_analyze.left not in seen:
		queue.insert(0, node_to_analyze.left)
	
	if node_to_analyze.right != None and node_to_analyze.right not in seen:
		queue.insert(0, node_to_analyze.right)


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

print("visita per livello:")
seen = []
queue = []
queue.append(root)
BFS(seen, queue)


for s in seen:
	print(s.value)
```
