# Architectural Pattern

## Architectural Design

Indica **come un sistema software deve essere organizzato** e qual è la **struttura del sistema**.\
L'output è come comunicano i componenti tra di loro

### A che serve e come è definito

Può essere definito in una fase iniziale ed è volutamente **informale,** infatti viene definito attraverso una **rappresentazione grafica** con i diagrammi E/R.&#x20;

Serve a mettere in discussione l'architettura utilizzata.

### Caratteristiche

* **performance**: se devo calcolare subito o delegare
* **security**: qualcuno inietta del codice malevolo
* **safety**: c'è un bug: l'aereo si spegne
* **availability**: sempre funzionante (uptime)
* **maintenance**: aggiornare le componenti

## Architectural Views

### Cosa sono

La notazione che uso per descrivere i modelli architetturali

### Come sono divisi

Si dividono in:

* **logical**: astrazioni
* **physical**: come sono distribuite le componenti sull'hardware
* **processi**: come il sistema interagisce a runtime
* **dev:** come viene decomposto

## Architectural pattern principali

* **MVC**: web-browser interagisce col controller che fa la richiesta e passa al model qualcosa da fare che verrà passato alla view. La view, fa la costruzione dinamica della pagina e restituisce al controller ciò che ha costruito, che poi verrà restituito al browser.&#x20;
* **Layered system:** tipo il modello iso-osi oppure un'app (frontend e backend)
* **Repository system**: shared repos (git) --> cartelle condivise
* **Client-server**
* **Pipe and filter:** processa input per produrre output (es. parser)
* **Application arch.:** design checklist
* **Transaction proc. system:** tipo l'aggiornamento di un database
* **Information system:** tipo la layered\
  browser -> login -> data in/out -> db
* **Web-based:** sito di e-commerce
* **Server implementation:** il server si occupa di qualsiasi operazione
