---
description: >-
  Appunti presi su carta a mano. Potrebbero contenere una grande quantità di
  imprecisioni. aa.2021-2022
---

# IUM - Raw

## Progettare un orologio

Specifiche:

* progettare un orologio da parete
  * ogni tanto la gente si gira e guarda che ore sono
  * regolare l'ora (avanti o indietro)
  * rimettere l'ora quando si scaricano le batterie
  * da legale a solare e viceversa

## Terminologia

### Affordance

Capacità di un componente di **far capire il proprio funzionamento,** senza che l'utente abbia bisogno di leggere le istruzioni (es. rotellina > long press button, perché il long press lo conosco solo se ho regolato altri orologi).

### **Labeling**

Etichetta da porre vicino a un pulsante o uno switch

### Interfaccia

Parte che l'utente vede, percepisce

### **Usabilità**

Organizzare un sistema software in modo efficace, efficiente e con soddisfazione, ossia **non sono frustrato** quando effettuo un'operazione sul sistema.

## Need Finding

Scoprire i bisogni dell'utente che andrà ad usare l'interfaccia.

Questo è possibile in diversi modi:

* **Osservare gli utenti: dove** cliccano, **cosa fanno** mentre eseguono questi task nel loro ambiente (es. Instagram --> che errori commette, di cosa ha bisogno)
  * La cosa migliore sarebbe osservare gli utenti non dando per scontato qualcosa ma **ex novo**.

Osservare ci permette di definire il problema --> contesto, stanza, posto, quando, somiglianze e differenze d'uso tra le persone

* **Lavorare insieme** agli utenti: vedere se usano trucchi, scorciatoie...
* **Far parlare** gli utenti: per vedere cosa fanno e cosa vogliono fare
* **Controllare** se gli utenti hanno veramente capito: molti potrebbero dire "si" ma magari sbagliano

Importante:

> Dalle necessità troviamo una soluzione, **NON** il contrario **Innamorati del problema, non della soluzione** -fondatore di Waze

Per fare need finding si utilizzano un paio di tecniche molto efficaci: **interviste** e **questionari.**

### **Interviste**

Le interviste sono un modo di fare need finding.

Sono **informali**, real-time (quindi puoi **modificare una domanda a tuo piacimento** ad esempio per essere più chiaro), mettono l'**utente a proprio agio** e sono **economicamente non espensive** (non spendi per fare interviste).

Le interviste sono time-consuming quindi è importante il target; a tal proposito, è importante registrare l'intervista, preparare le domande, prendere appunti, cercare di incoraggiare ad approfondire le risposte, evitare domande scontate o troppo specifiche.

**Non** fare la domanda **quante volte**: è molto **difficile rispondere alle domande che chiedono la frequenza** di una certa azione; **meglio chiedere un dato preciso** (es. Ieri hai mangiato la pasta?)

### **Questionari**

I questionari sono un modo per raccogliere tantissimi feedback anziché fare interviste singole.

Le domande sono di tantissimi tipi: a risposta multipla, a risposta singola, aperte...

L'utente spazia di meno, ma se il questionario è fatto bene inserirà più risposte.&#x20;

### **Altri modi per raccogliere feedback**

* **Diario**: strumento per prendere appunti in ordine cronologico
* **Visual Camera**: registro le interazioni degli utenti (tramite ad esempio strumenti come Hotjar)

## Task

I task sono i **compiti che l'utente fa per soddisfare un certo need** e raggiungere un certo obiettivo.

Devono essere:

* **efficienti** --> agile, non vogliamo perdere tempo
* **comprensibili** --> non ambigui
* **di facile comunicazione nel team** --> comprensibili a tutto il team

## Storyboarding

Dobbiamo decidere **quali need soddisfare** con la nostra interfaccia: **perché** le persone vorrebbero usare la nostra interfaccia? **Che vantaggio** avrebbero? Cosa dovrebbe permettere loro di fare?

* Una sorta di "vendere la UI".

Ci interessa capire il ruolo che avrà la UI, non le sue funzioni: capire **chi** è coinvolto (es. nell'appello: docenti e studenti. I guardiani non c'entrano nulla), l'**ambiente** (aula, non tutti gli studenti hanno un computer...) e tutte le **informazioni di contorno**.

**NON** progettiamo le schermate e i bottoni: approccio top-down: cominciamo dalle cose ad alto livello e man mano uno scende. Quando finalmente abbiamo capito tutti i need, possiamo effettivamente progettare le interfacce che risolvono i need. Disegnare la UI infatti, significherebbe non ragionare sul need, e quindi **se pensassi a un bottone o un dropdown sarebbe problematica come cosa.**

Negli ultimi anni si è diffusa l'idea di fare **storyboard**: dei segni semplici e chiari di che cosa succede **per ogni task, max 4 vignette e massimo 4 storyboard totali**.

Non si possono disegnare le schermate nel fumetto: non astraiamo più ma entriamo nel dettaglio, **non dobbiamo disegnare** screen nel fumetto.

## Rapid prototyping

**Prima progettare il prototipo rapidamente e poi realizzarlo** così se lo debbo buttare sono felice

Il prototipo non mostra requisiti non funzionali:

* velocità del servizio
* tempo di risposta
* affidabilità (non so quanto regge il sistema)
* sicurezza

Cose che si possono testare su carta:

* labelling (testo valido / comprensibile o non comprensibile)
* funzionalità (bottone se funzia o no, e testiamo il prototipo contemporaneamente)
* navigazione all'interno del prototipo

### Wireframe

Rappresentazione molto semplice di quello che voglio fare a livello grafico (non a livello di UI)

* Ergo: **Lorem Ipsum no**

Anche se sul cartaceo sembra brutto, in realtà è molto professionale il risultato perché permette di fare rendere conto all'utente dell'idea di UI. I contenuti devono essere veri, e non abbozzati come il Lorem Ipsum.

## Testing

### Funzionalità vs. usabilità

Test sulla **funzionalità**: input e output

Test **usabilità**: possibilità di utilizzo di un sistema secondo tre principi: efficacia, efficienza e con soddisfazione.

* **Efficacia**: che raggiunga gli obiettivi prefissati
* **Efficienza**: veloce
* **Con soddisfazione**: l'esperienza non è frustrante

### Scopi

Identificare problemi

* vedere come reagiscono su una **nuova funzionalità**
* vedere come reagiscono sulla **nuova interfaccia**

La quantità ideale di gente è 3 / 5 persone.

### Passi

Costruire uno scenario, descrivere una situazione nel quale l'utente si trova. Es. siete in due e volete andare a Parigi il primo Novembre. Avete un budget limitato e non avete più di 100 euro

Osservare che task vengono fatti.

### Mago di Oz

Interfaccia che simula il funzionamento reale mediante l'intervento umano.

Il prof allude a qualcuno, un umano, che cerca di **simulare il funzionamento di un'interfaccia**

* Esempio: il test venne fatto con delle segretarie di azienda: doveva prendere appunti e poi trascriverli sul computer **(IBM)**.

Dalle osservazioni fatte vennero fuori dei problemi: uno tra tanti è il fatto che alcuni argomenti non potevano essere dettati perché riservati.

L'interfaccia:

* deve essere **interattiva**
* chi la gestisce è un omino che deve rimanere **nascosto**

Svantaggi:

* non fedele
* la tecnologia potrebbe non essere mai sviluppata
* alcune caratteristiche possono non essere simulate (es. taxi radiocomandati)

Abbiamo **due tipi di prototipi**:

* **lofi examples:** esempi a bassa fedeltà; gli utenti sono più inclini a lasciare commenti
* **hifi examples**: esempi ad alta fedeltà, belli da vedere; focus sul loro comportamento

### Laboratorio Vs Campo

**Laboratorio:** abbiamo **equipaggiamento specialistico** (tutto l'occorrente), **ambiente senza interruzioni** ma non riusciamo ad osservare gli utenti che collaborano.

Es. provo zoom in aula non va, provo Zoom in laboratorio: tutti i computer cablati con connessione veloce ecc...

**Campo:** ambiente naturale e viene mantenuto il contesto, meno distrazioni.

## Strategie

**Questi metodi sono soggettivi**: dipendono da un sacco di fattori propri di ogni esaminatore e anche la risposta dell'utente è soggettiva.

I dati prodotti devono essere **qualitativi**, **non numerici**.

### Think Aloud

Dire all'utente di spiegare **passo passo a voce alta** cosa sta facendo.

### Cooperative evaluation

Porsi in maniera empatica nei conronti dell'utente: infatti, sarà più propenso a usare un'interfaccia senza stress.

### Post-task Walkthroughs

Come prima, ma faccio rivedere la registrazione all'utente e gli chiedo maggiori informazioni sulle sue scelte (cosa ha fatto, perché ha sbagliato ecc). Lo faccio rivedere o subito dopo o a distanza di tempo. Il vantaggio è che **l'utente si ricorda tutte le azioni che ha fatto** perché le ha fatte lui.

## Esperimenti

### Variabili dipendenti vs. indipendenti

* **dipendenti**: dipendono dall'utente (es. quanto tempo ci mette un utente a premere un bottone)
* **indipendenti**: quelle indipendenti dall'utente, e che possiamo cambiare (es. alcuni bottoni, menù...)

### **Ipotesi**

Previsione che dice che la variabile dipendente cambierà in funzione di una variabile indipendente.

### **Ipotesi nulla**

Previsione che dice che la variabile dipendente **non** cambierà in funzione di una variabile indipendente.

### Within vs. Between Groups

**Within Groups:** ogni soggetto esegue l’esperimento **sotto le varie condizioni**.

**Between Groups:** ogni soggetto esegue l'esperimento **su una sola condizione**.

Se si usa il primo approccio, allora succede che l'utente ha difficoltà quando usa il sistema con ogni condizione, perché deve re-imparare da capo ogni volta.

Nel secondo caso, è più semplice per l'utente, perché impiegherà tutte le sue forze per completare il task e quindi l'energia viene focalizzata su un singolo task e su una singola interfaccia.

### A/B Testing

Solitamente dividi i gruppi in due:

* gruppo di controllo
* gruppo che fa la condizione sperimentale

Non dobbiamo concentrarci sugli outlier, che sono i cosiddetti casi "border-line".

Si possono avere due approcci.

****
