# 🖥 Linguaggi e Compilatori

## ER: costruire NFA a partire da un'espressione regolare

Ci sono due passi fondamentali:

1. Costruire l'**albero astratto**. Per farlo basta "risolvere" l'espressione regolare in maniera "spezzettata", a blocchi di parentesi.
2. **Disegnare l'automa** NFA **a pezzi**

### Testo d'esempio

L'espressione è la seguente:

```
(a|c)*(c|b)*(abc)*
```

### Regole per fare l'albero astratto

Regole da tenere ben presente:

1. L'associatività **a sinistra**
2.  OR (a|c):

    ```
      |
     / \
    a   b
    ```


3.  AND (abc)\*:

    ```
          *
          |
         / \
        °   °
       /     \
      °       c
     / \
    a   b
    ```

### Passo 1: l'albero astratto

```
            °
           /  \
          /    \
         /      \
        /        \
       /          \
      °            *
     / \            \
    /   \            °
   *     *          / \
   |     |         /   \
  / \   / \       °     c
 a   c c   b     / \
                a   b
```

### Passo 2: l'automa

Mi disegno i vari automi e li unisco tra loro.

### Regole per disegnare l'automa

* Disegno prima gli automi semplici (atomici, esempio, automa che riconosce a, automa che riconosce c) e li unisco
  * Sebbene possa aver disegnato già un altro automa in precedenza che facesse la stessa cosa, per ogni ramo **devo disegnare un automa diverso**\
    Esempio: se ho già disegnato un automa che riconosce a e mi ritrovo a dover disegnare un ramo con un automa che riconosce a **devo disegnarlo di nuovo**
* **Concatenazione (or)**
  * aggiungo uno stato vuoto iniziale
  * faccio due branch con gli automi creati in precedenza
  * aggiungo uno stato vuoto alla fine
  * i due stati supplementari avranno epsilon nelle frecce
* **Unione (and)**
  * prendo i due sottoautomi e li unisco tra loro andando a creare un nuovo stato
  * quest ultimo avrà come nome "stato finale sottoautoma1 / stato iniziale sottoautoma2"
* **Kleine (\*)**
  * come concatenazione (stati supplementari) ma al primo fai una freccia che va all'ultimo e il penultimo va nel secondo. Ovviamente entrambe le frecce hanno epsilon.&#x20;

### Disegno dell'automa

Guardando l'albero astratto, parti dall'estrema sinistra e cominci a fare piccoli sottoautomi. Man mano che risali l'albero unisci a seconda di quello che trovi.

![disegno dell'automa finale, derivante dall'ER](<../.gitbook/assets/image (2).png>)
