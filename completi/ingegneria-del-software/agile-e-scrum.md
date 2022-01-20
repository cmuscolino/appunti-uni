# Agile e SCRUM

## Agile

Deriva dall'esigenza di sviluppare software **presto e bene**

Per il Plan Driven posso farmi pagare per quello che consegno, l'altro invece sul tempo dedicato al progetto.

1. Delivery frequenti
2. **Tanto testing: poiché devo fare tanti delivery**
3. Code over documentation

Questo modello alterna tra requirements engineering e implementation.

AGILE si focalizza sul codice piuttosto che sul design.

### Condizioni di utilizzo

Questo modello può essere utilizzato **solo in team molto piccoli**, max 7 persone nella stessa location, altrimenti non funziona.

Il cliente deve essere disposto a accettare di fare riunioni per lasciare feedback.

### I principi

1. Il **customer deve essere coinvolto**: mi serve che lui mi dica se va bene oppure no, poiché non sto documentando nulla
2. **Delivery incrementale**
3. Focus sulle **persone, non sui processi**: essendo che il team fa in qualche modo i requisiti, bisogna essere solidali nel senso che la responsabilità è solidale e lo sviluppo è solidale. Nell'agile tutto il team è responsabile: se fallisce qualcosa è colpa del team
4. Embrace change
5. Mantenere la semplicità: **keep it simple**. Se è semplice, posso metterci le mani, altrimenti no. **Non c'è documentazione**, il software deve parlare da solo.

### Approcci

* **extreme programming (XP)**: approccio estremo allo sviluppo, ogni giorno il software viene costruito, al cliente viene consegnato ogni due settimane e tutti i test devono essere eseguiti prima di ogni build
  * avviene in questo modo:
    * definisco gli use case dal cliente
      * **user story**: la trama, il cliente spiega di cosa ha bisogno, esattamente la descrizione del sistema di ciò che lui vuole
    * definisco i requisiti e i task
      * dalla user story definisco i vari task, cioè quello che il sistema deve fare. Ovviamente essendo uno sviluppatore, devo vedere un attimo se sono fattibili le cose che mi chiedono.
      * codice flessibile: nonostante il cliente mi chieda "3 prodotti", devo fare l'array di prodotti di lunghezza N perché non si sa mai. Ovviamente essendo un parametro posso facilmente cambiarlo
    * pianifico un attimo che devo fare
    * sviluppo e testo
    * ricomincio
  * **pair programming**: si lavora in coppia
  * **continuos integration**: quando un task è completato viene integrato nel sistema. Tutti i test devono passare ovviamente.
  * **refactoring**: riorganizzazione delle classi, cleanup nomi attributi e metodi (mancando la documentazione il codice deve parlare)
  * **test-first development:** ogni volta che faccio un cambiamento testo il mio sistema. Se va tutto bene allora lo integro.
    * non esiste un insieme di test che copra tutti i casi possibili e immaginabili

Funziona su **gruppi piccoli**.

## Scrum

* **Scrum**: metodo Agile
  * fase1: **planning**, obiettivi generali e faccio il design dell'architettura software (analisi requisiti e definizione dell'architettura, rientrano in gioco i principi del plan driven)
  * fase2: **sprint di sviluppo** --> ad ogni ciclo faccio un incremento del sistema (che ho già pianificato, il manager lo sa già cosa ho fatto)
  * quando un progetto chiude, si completa la documentazione

Lo scrum è quello più ampiamente usato.

### Fasi

* guardo il lavoro che c'è da fare (anche guardando il backlog)
* pianifico
* sprint (eseguo) e genero un backlog --> faccio dei meeting e faccio la review per quel test
  * lo sprint dura due-quattro settimane
* ricomincio

Lo **scrum master** schedula i meeting, tiene conto del backlog, parla col customer e tiene traccia del progresso. **è il project manager**

### Vantaggi e svantaggi

Benefici:

* prodotto suddiviso in piccole parti maneggiabili
* i requisiti "impossibili" non impediscono al progetto di andare avanti
* tutto il team sa tutto

Svantaggi:

* non essendoci documentazione, è un problemone per la gente che viene dopo di me
