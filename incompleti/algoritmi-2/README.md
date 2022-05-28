# 🌡️Algoritmi 2

## Ripasso

### Pensiero Computazionale

1. Formulazione non ambigua con linguaggio matematico
2. Trovare i passi logici che permettono di risolvere un problema
3. Codificare un programma
4. Testare una soluzione

### Formulazione ambigua vs. non ambigua

La formulazione non deve essere ambigua quando si parla di un problema

Ambigua: trova il mio più caro amico su Facebook

Non Ambigua: media di 100 numeri

### Algoritmo vs. Implementazione

**Algoritmo**: descrizione informale del problema e viene valutato in termini di correttezza ed efficienza (in termini di spazio e tempo)

**Implementazione**: come viene attuato in un certo linguaggio

### Tecniche algoritmiche principali

* Le principali tecniche algoritmiche studiate all'interno di algoritmi 2 saranno:
* greedy
* divide et impera
* programmazione dinamica
* backtracking

## Grafi

### Terminologia base

Concetti fondamentali:

* **cammino (path)**: è una passeggiata dove non si passa mai più di una volta su un vertice
* **passeggiata (walk)**: sequenza vertice, arco, verti, arco... che indica uno spostamento all'interno di un grafo da v1 a vN usando gli archi del grafo
* **ciclo (cycle)**: cammino dove il primo vertice coincide con l'ultimo
* **concetto di connessione**: U -> V significa V è raggiungibile da U
* **componenti connesse**: sottoinsieme di vertici che sono connessi tra loro
* **albero**: un grafo con num. archi = num. nodi - 1
* **albero radicato**: da un albero prendo un vertice e lo scelgo come radice
* **foresta**: un insieme di alberi

### BFS e DFS

{% content-ref url="dfs.md" %}
[dfs.md](dfs.md)
{% endcontent-ref %}

{% content-ref url="bfs.md" %}
[bfs.md](bfs.md)
{% endcontent-ref %}

