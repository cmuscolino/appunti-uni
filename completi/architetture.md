---
description: >-
  Ovvero una pratica guida su come sopravvivere allo scritto del Mei. Autori:
  Damiano e Marzia Bragaglia. Special thanks to: Stefano e Paolo (Mastro Paint).
  13.01.2020
---

# 🖨️ Architetture

## Risolutore di esercizi

Non ti basta questa fantastica guida? C'è anche il risolutore di esercizi su Github! [architecture-helper](https://github.com/sgravato-productions/architecture-helper) così in caso inventi altri esercizi o ne trovi altri puoi testare la correttezza delle tue soluzioni.

## Pipeline (disegnare la pipeline)

### Testo

Scrivere il numero dei colpi di clock dimostrando la correttezza con lo schema della pipeline. Disegnare tutti gli stadi della pipeline basandosi su un codice assembly.

### Codice assembly

```
lw s3, 4(s3)
add s3, s0, s1
lw t4, 8(s3)
sw t4, 8(t1)
add t7, t4, t1
lw t2, 8(t7)
add t2, t2, t1
add t2, t2, t7
```

### Regole

* La **bolla** si mette sempre nella **fase ID**
* Quando si mette una **bolla** si scala SEMPRE di **due stati**

### **Svolgimento**

1. **lw:** nessun problema
2. **add**: nessun problema: scrivono entrambe il registro s3, l’add va a modificare dopo l’lw. Ci sarebbe stato l’hazard solo se add avesse usato s3 come dato, in quel caso ci sarebbe andata una bolla.
3. **lw**: forwarding da EX della add ad EX della lw.\
   Con questo fwd mi sto prendendo il valore corretto di s3 dopo che è stato calcolato dalla ALU nella seconda istruzione. Se non facessi forwarding la lw prenderebbe un valore vecchio di s3.
4.  **sw**: ci servono una bolla e un forwarding.\
    La bolla ci vuole perchè c’è un hazard “load-use” tra sw e lw, il forwarding perché il valore corretto di t4 è all’uscita di MEM: viene scritto e letto contemporaneamente il registro t4.\
    \
    **NB: NON si può fare** forwarding da MEM a MEM, perché nonostante il registro t4 non venga modificato dall’elaborazione della ALU, nell’istruzione t4 dovrà essere inserito nel campo rs1. Bisogna tener presente il formato interno dell’istruzione sw.\
    \
    \| offset | rs2 |rs1 |funct3 | offset | opcode\


    Nel nostro caso:

    * rs1 è t4
    * rs2 è t1
    * gli altri campi non ci interessano per il nostro ragionamento

    E’ vero che il compito della ALU in questo caso è solo quello di calcolare l’indirizzo corretto sommando l’offset a t1, ma bisogna tener presente che l'istruzione è un “pacchetto” di informazioni compatte, che viaggiano insieme. Ciò vuol dire che dallo stadio Instruction Decode vengono mandati alla ALU tutti i registri interessati con i loro contenuti (più ovviamente l’opcode e funct3 che servono a definire il tipo di operazione da eseguire). L’unico punto in cui posso “modificare” il contenuto dei registri per prendere i valori corretti è alle due entrate della ALU, in effetti i due MUX che vediamo nell’architettura con Pipeline servono esattamente a questo.
5. **add**: non ci sono problemi. La sw non scrive su t1, prende soltanto il valore che contiene per calcolare l’indirizzo in memoria in cui deve memorizzare t4. Con la sw non viene “eseguito” Write Back, perché la sw scrive in memoria e non nei registri. Per questo motivo l’istruzione sw non vale come 2 istruzioni nel calcolo degli accessi del loop (vedere esercizi sul miss rate).
6. **lw**: forwarding per il valore aggiornato di s7
7. **add**: bolla: lw scrive in t2, poi il contenuto di t2 aggiornato viene preso dalla add tramite forwarding.
8. **add**: fwd tra l’ultima add e la penultima per il valore aggiornato di t2.

Contiamo gli spazi sotto i vari stati ottenuti.

![](https://lh6.googleusercontent.com/wIRvLBlHuml6vqkuGKtJYTN7cpetLZwt61rWTPCvSPYNzDL1ezmGb6E5iJCK2k8SGlWcX9DDLEWvz\_9-TUS3L4fQU3OlbS51SrasC6hqkd589vmcghKFwiQb0suXR3ujvzJE0nH2)

## Calcolo del miss rate

### Testo

Cache one-way 16 set con **blocchi da 128B**. Abbiamo una **lista linkata di 4096 nodi**

```
.data
	primo_nodo_lista: .word 7, prossimo_nodo
.text
	la s0, primo_nodo_lista
	mv s1, zero
loop:	lw t0, 0(s0)
	add s1, s1, t0
	lw s0, 4(s0)
	bne s0, zero, loop
	li a7, 10
	ecall
```

### Regole

* le istruzioni LA, LW, LI -> tutto quello che fa il load sui registri, sono sia istruzioni che accedono in memoria che scrivono. Di conseguenza bisogna considerare sia l’accesso in memoria che per i dati.

### Svolgimento

Abbiamo un blocco i e un blocco j che corrispondono rispettivamente al blocco relativo ai dati e alle istruzioni.

1. I nodi di una lista sono formati da due word, una per l’elemento e la seconda per il puntatore al prossimo nodo, quindi 4096 nodi occupano in memoria\
   &#x20;         4096 \* 8 = 32768 byte
2. Abbiamo blocchi da 128 bytes, quindi per memorizzare l’intera lista ci vogliono

&#x20;               32768 /128 = 256 blocchi

Ed in ogni blocco avremo

&#x20;               128 / 8 = 16 nodi

Passiamo al **calcolo del numero di miss sul blocco 0**. Per comodità consideriamo che sia il blocco istruzioni sia il blocco 0 dei dati vengano memorizzati nel set 0.

Abbiamo già il blocco j (istruzioni) caricato nella cache quando entriamo nel loop: il blocco viene caricato alla prima istruzione..

Entriamo nel loop: abbiamo un hit nelle istruzioni ed un miss per i dati (LA) quindi rimpiazziamo j con i (dati).

ADDI:miss per le istruzioni, carico j nella cache

LW: miss per i dati, carico i nella cache.

BNE: miss per le istruzioni, carico j nella cache ed esco dal loop.

Questa situazione si ripete per le prime 16 iterazioni (da 0 a 15), poiché in ogni blocco ho 16 nodi.  Questo porta ad un miss rate parziale di 4/6 per le prime 16 iterazioni

NB: ricordiamo che nel calcolo del numero di istruzioni nel loop le istruzioni lw, li, la valgono 2.

Nell’iterazione 16 mi ritrovo con il blocco j caricato nel set 0 (perché l’ultima istruzione del loop è bne e come abbiamo visto mi fa caricare il blocco j nella cache, non accedendo a nessun dato).

Ho un miss per i dati per il nuovo blocco. Il blocco i+1 viene quindi caricato nel set 1 dopodiché per le prossime 15 iterazioni avrò hit sia per i dati che per le istruzioni non essendoci più conflitti (le istruzioni sono sempre nel blocco j caricato all’inizio, i dati devono essere caricati ogni volta ed utilizzati).

**Trucco**: le iterazioni per set, intese come numero di elementi contenuti in un solo blocco, si trovano facendo:

* (dimensione blocco) / (dimensione del singolo nodo) \[v. punto 2]

**Il miss rate** possiamo calcolarlo con questa formula:

* numero miss nella cache / (num. accessi in memoria \* numero dei set \* iterazioni per set)

Non è necessario calcolare i miss su tutti i dati, perché dopo i primi 16 blocchi si ripete tutto, quindi possiamo prendere solo i primi 16 blocchi per il calcolo. In questo caso

* **Miss Rate** = (4\*16)+(1\*15) / (6 \* 16 \* 16)

![](https://lh4.googleusercontent.com/Aw1vnOp\_d2OwTzWJhENb6pV5gIsEUlOZGfarsBSC616jou\_j5GknEkKC3jHAi9m6fungtaknBMPnLPBiXCkKZGUvRTycuWeD0fPgio4GtG\_m-BqpdugDGZsEv9scgQcvYLPqusZi)

***

## Calcolo page-fault e miss-rate TLB

### Testo

Per comodità prendiamo gli stessi dati dell’esercizio per il miss rate.

Consideriamo pagine di grandezza 4096 byte, grandezza standard.

### Procedimento

1. Calcolare il **peso Data-Segment**: 4096 (word) \* 8 (byte) = 32768\
   \
   Gli 8 byte vanno messi perchè si tratta di una lista, che è composta da valore attuale + indirizzo della word successiva\
   \
   Se si fosse trattato di un vettore avremmo dovuto mettere “4 byte” e non 8 (infatti un vettore è un insieme di word).\
   \
   Se si fosse trattato di un B-Tree avremmo dovuto mettere 12 byte (elemento, link ai nodi figli)
2. Trovare il **numero di pagine per i dati**: divido il peso calcolato per la dimensione delle pagine\
   \
   32768 / 4096 = 8 pagine per i dati
3. Trovare il **numero totale di pagine**: basta sommare uno (la pagina per il codice) alla pagina per i dati (8 + 1 = 9)

Avendo il numeratore, calcoliamo ora il **miss-rate della TLB**:

* numero pagine / numero elementi della lista \* (accesso ai dati + accesso alle istruzioni)

N.B. in questo esercizio il numero degli elementi nella lista è uguale alla dimensione della lista. Nella formula va **incluso il numero degli elementi nella lista e NON la dimensione**

* Miss rate nella TLB = 9 / (4096 \*(4+2)) = 0.03%

![](https://lh6.googleusercontent.com/0TvgmdiytNBYQF\_tVY-aX5U71qsCVxu39VFkS7-Al7Bdciv0cbHr1wlNRtnaBAYwQbNXHPgp1VX8B-b1\_GOTISSQr-S\_nyHUZZKjg6mM-5XiX0P7BMk2krbYuZDYJKT3TFyhVHqD)

## Page-fault con albero binario: (11/06/2015)

### Dati

* pagine da 4096
* 16 nodi da 3 word ciascuno -> parliamo di un albero binario, quindi ogni nodo ha 3 word: una per l’elemento e due per il collegamento ai figli, quindi ogni nodo pesa 12 byte

### Svolgimento

1. Calcoliamo **l’altezza dell’albero** (col disegnetto perché non abbiamo molta voglia di trovare l’algoritmo). Nel caso di un albero binario bilanciato l’altezza è log(n)  dove n è il numero dei nodi. Nel nostro caso l’altezza è 4
2. Avendo 16 nodi, e ogni nodo pesa 12 byte calcoliamo il **peso totale del data segment**:\
   \
   16 nodi \* 12 byte = 192 byte
3. Sappiamo che possiamo inserire tutti i 192 byte in una pagina sola, quindi avremo 1+1 = 2 pagine, una per i dati e una per il codice.

Ora bisogna calcolare lo **spazio occupato nello stack**: ogni chiamata ricorsiva creerà uno spazio di 12 byte (addi sp, sp, -12)

Nel caso di un codice ricorsivo su una lista dovremmo moltiplicare il numero degli elementi della lista \* 4, perché lo stack si ingrandisce mano mano di una sola parola per volta.

Nel caso di un albero bisogna trovare l’altezza massima (proprio come in questo esercizio), bisogna fare:

* (spazio occupato nello stack) \* (altezza massima dell’albero + 1) = 12 \* 5 = 60

Il 5 è dato dall’altezza dell’albero (4) + 1 che sarebbe il livello radice, normalmente non si conta.

Siccome 60 byte possono essere contenuti in una pagina (le pagine sono grandi infatti 4k) abbiamo 2 pagine precedentemente calcolati + 1 pagina, quella dello stack.

Di conseguenza avremo 3 pagine.

* Miss rate nella TLB = sempre la solita robbaH --> numero pagine / numero elementi della lista \* (accesso ai dati + accesso alle istruzioni)

![](https://lh6.googleusercontent.com/cF9rK5dJ5bKjOkqtAoVrS9b-LQAKKFyTOxeSd7M8QfZ8YTq-otFTR3mOIdqjDejpVOHBJNVs3OXClDSyO\_E05N-0LqBxZpi\_LfcRgKKkOro2KnIArICkYuZpkM30aKFo7vbs2L5I)

## Esercizio Miss-Rate Lista

![](https://lh4.googleusercontent.com/OMvfC8IPpge0xhzYTt-fXSLrXm5zxIpGZvwcS3enyPD8CUI2fbd\_RREtk1J2gYJIKijHIp-C4wsCejI-CsxfUr2PUdWHHtG8JmePWr16XRZ25RyQFbTPmv0eAtKfTZezlKjPLSi\_)

## ✨Calcolo hit-miss✨

### Testo

si hanno questi accessi in memoria: 24, 64, 164, 32, 208, 128, 44, 192, 432, 452, 88, 212, 504, 384, 32, 52, 292, 232, 388, 400, 404, 288, 40, 376

Calcolare hit-miss in una cache 2-way con blocchi da 32 byte.

### Mantra

Il mantra è:

“blocco? set? hit/miss?”

Blocco: indirizzo // dimensione del blocco (parte intera)

Set: blocco % (modulo) numero set nella cache: resto della divisione

Miss: quando non è caricato il blocco che contiene l’indirizzo nella cache.

### Svolgimento

In questo caso:

Blocco? 0 (24 // 32 = 0.75)

Set? 0 % 32 = 0

Hit or Miss? Miss (il blocco 0 non era mai stato caricato in memoria)

***

## Esercizio Sbatti di zio Gianni (metodi di ottimizzazione)

```
loop: 	lw t2, 0(t0)
        add s0, s0, t2
        addi t0, t0, 4
        addi t1, t1, -1
        bne t1, zero, loop
```

Per **contare i colpi di clock “ad occhio”**: numero istruzioni+bolle (load-use e branch)

In questo caso abbiamo 5 istruzioni (5) + una bolla (1) tra la prima e la seconda istruzione + la branch (1). Dunque abbiamo 7 colpi di clock \* N , dove N è il numero di iterazioni del codice

Questo in caso normale, dove non si considera la branch prediction. Se assumiamo la presenza di branch prediction possiamo togliere un CC alla fine.

### **Metodi di ottimizzazione**

* **Branch Prediction:** implementando una branch prediction risparmio un colpo di clock ogni iterazione.
* **Riordino**: eliminando la bolla tra le prime due istruzioni, ovvero risolvendo gli hazards, in questo caso si può scambiare la prima addi con la add (terza e seconda istruzione) ed eliminando così la dipendenza.
* **Pipeline Dual-issue (o LIW)**: con il loop unrolling si “srotola” il loop n volte e si riordinano tutte le istruzioni risultanti, sempre tenendo in considerazione le dipendenze.

### Riordino

Cambiare l’ordine delle istruzioni per eliminare gli hazards, ma senza compromettere la logica del codice.

### Dual issue SENZA loop unrolling

Si tratta di “rappresentare” il codice in forma tabellare per permettere di impacchettare le istruzioni due a due.

La tabella dovrà contenere:

* a sinistra le istruzioni relative alle branches e alla ALU come addi sub ecc...
* a destra tutte le altre istruzioni la sw li ecc...

Nel riempimento della tabella, ogni qualvolta che c’è una bolla bisogna “saltare” un colpo di clock (nella tabella tutte le istruzioni con dipendenze devono essere ad una riga di distanza)

Per usare la tabella Dual-issue, dobbiamo prima srotolare il loop n volte. Nel nostro caso il loop unrolling è di 2 volte.

### Dual issue CON loop unrolling

```
loop:   lw t2, 0(t0)
	add s0, s0, t2
        lw t3, 4(t0)
	add s0, s0, t3
        addi t0, t0, 8
	addi t1, t1, -2
	bne t1, zero, loop
```

**Srotolare il loop** vuol dire **duplicare il loop e ottimizzarlo**: anziché aggiungere un elemento solo ne aggiunge DUE alla volta.

Occorre specificare che si presuppone che il numero degli elementi sia pari.

Ora si va a **calcolare l’ottimizzazione:**

* 7 istruzioni (del codice)
* 3 bolle: prima e seconda istruzione, terza e quarta istruzione, la branch.
* colpi di clock con l’unrolling: (7 + 3) / 2 (perché abbiamo utilizzato l’unrolling) = 5cc di morfina

| ALU / branch    | lw/sw        |
| --------------- | ------------ |
| addi t1, t1, -2 | lw t2, 0(t0) |
| addi t0, t0, 8  | lw t3, 4(t0) |
| add s0, s0, t2  | NOP          |
| add s0, s0, t3  | NOP          |
| bne t1, zero, 0 | NOP          |

Abbiamo 5 CC + 1 della branch per due iterazioni. Quindi in totale abbiamo 6 / 2 = 3 CC per ogni iterazione.

Scendono a 2,5 CC ad iterazione se assumiamo la presenza di branch prediction.

![](https://lh4.googleusercontent.com/lvonwjzhG-ZPQgNZVXxL4PpZUlb7SfiDErnRpclidCyarr1vHvQktLmQmZL7duXjSMwucAWoheb3l2sCv3b-h9Y1u74xC9GgW94NoMxF2Mx52ko8HPj9xCbGouDn-ZxoV-FYw4n3)
