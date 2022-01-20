# I diversi tipi di test

## I diversi test

### Unit testing

Testo le singole funzionalità dati pre e post condizioni

È **automatico.**

### Component testing

Metti insieme più funzionalità per fare qualcosa (testi interfacce).

Cosa vado a testare:

* i null
* designo i test in modo tale che falliscano
* stresso il sistema

### System Testing

Connetto e integro componenti già testati. Vado a testare il sistema nella sua interezza.

### Release testing

Dimostro che il sistema è quello che richiede l'utente, quindi è corretto e fa vedere che funziona per quello che era stato progettato

### Requirements Based Testing

Mostro che per ogni requisito c'è almeno un test.

## Coverage

Come faccio a stabilire che ho testato a sufficienza?

Con lo unit testing ad esempio c'è la level coverage: grafo orientato con if-else, ed entro nei vari branch.

## Automazione

Normalmente nei test ci sono:

* **initialization**: definisci i test case con input, expected output
* **call**: chiami il test
* **assertion**: compari i risultati ottenuti con quelli aspettati

## TTD

**I test prima di tutto**. Posso continuare a sviluppare solo se passo i test.

Benefici:

* code coverage: ogni segmento ha almeno un test
* regression: controllo se integrando non ho rotto tutto
* simplified debug: so subito dove ho sbagliato
* documentazione: definisco cosa il software fa

