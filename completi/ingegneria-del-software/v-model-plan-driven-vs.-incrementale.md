# V-Model, Plan-driven vs. Incrementale



Il processo sw è un insieme di attività che modelliamo come un processo. Questo processo coinvolge anche l'organizzazione di esso, l'input di questo processo sono i requisiti (per questo si può parlare di sviluppare i requisiti, che non per forza definisce le specifiche); i requisiti sono le cose che l'utente, come lo vuole lo decido io.

### Plan driven vs. Incrementale

Nello sviluppo plan-driven **faccio tutto il piano e dopo inizio a implementare e testare,** facendo sempre il testing nelle fasi avanzate, se mi accorgo di un errore devo reworkare tutto (es. cambiano le specifiche devo riscrivere tutto da zero).

Nello **sviluppo incrementale invece no; testo lungo la strada** ma non so quanto sono lontano dal progresso.

### Riuso

Vado a implementare roba già esistente

### V-Model

È il modo classico di implementare un plan-driven: si chiama così perché possiamo immaginare una V; richieste --> unit-test --> serv

1. **Unit Testing** vado a testare le singole funzioni, va a vedere l'output per vedere se il programma funziona
2. **Integration testing**: testo se i pezzi nel complesso funzionano tra di loro (interfaccio più unit test)
3. **Acceptance testing**: lo faccio con i dati del cliente
4. **Consegna al cliente**: e spero che mi paga (cit)

Il software deve essere progettato in maniera scalabile: altrimenti se volessi implementare nuove funzioni dovrei cambiare tutto; **bisogna progettare tutto in "singole parti"**.

### Prototipo - System Prototyping

Una versione sviluppata rapidamente, giusto per vedere se il consumatore vuole effettivamente ciò che sto sviluppando o no;&#x20;

Ovviamente dipende da quanto è sviluppato il prototipo: se è basic si può tranquillamente scartare in fase di sviluppo.

Quando il delivery viene fatto **incrementalmente**:

* **definisco** i requisiti e mi **focalizzo** su quelli più importanti
  * che **possono cambiare** in fase di sviluppo
* **assegno** i requisiti a "unità di tempo" (li ordino)
* li **sviluppo pian piano**
  * e ciò comprende anche una **fase di test** ovviamente Se non ci sono altre modifiche, il progetto può essere considerato come terminato

Problemi:

* **incremento più volte la stessa cosa**: quindi capita che due gruppi implementano due volte la stessa cosa
* le specifiche sono definite man mano che faccio il sistema

### Misure e metriche

Le misure per migliorare il software sono:

* measurement: attributi del software
* analysis: tempo che ci mette, debolezze
* change

Metriche sono **tempo** e **effort**.

* tempo: **quando** lo consegnerò
* effort: 10 person / month; è una **misura di effort**.

### Capacity Maturity Model

Modello creato per stabilire quanto un processo è maturo o no

1. Initial: il punto di partenza, non si è fatto quasi nulla
2. Repeatable: è stato documentato in maniera tale che si possono ripetere le stesse azioni
3. Defined: è ben definito, quindi le fasi sono chiare
4. Managed:
5. Efficient (optimized): ottimizzazione
