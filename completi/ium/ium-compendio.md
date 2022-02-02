---
description: Appunti presi (e rielaborati) dalle slide del professore. aa.2021-2022
---

# IUM - Compendio

Compendio che mira a spiegare tutto ciò che è stato fatto durante il corso.

## Need Finding

Il concetto chiave è **osservare** gli utenti nel loro ambiente, per individuare le loro **necessità**, comprendere i loro **obiettivi** ed identificare i problemi esistenti.

Quando si osserva, lo si fa a “cuor leggero”, **senza dare per scontato alcunché** e senza avere già in mente quello che cerchiamo.

Cosa osservare: qualunque cosa, anche singoli dettagli (es. contesto, momenti della giornata).

L’osservazione può essere **attiva** o **passiva**: in quella attiva **coinvolgi l’utente** attraverso interviste e questionari, in quella passiva **passi del tempo con lui** senza disturbarlo o analizzando video.

Intraprendendo un’osservazione attiva, bisogna essere **open minded** cioè ascoltare gli utenti, concentrarsi su ciò che loro dicono, lasciandoli parlare, soprattutto quando raccontano di ciò che fanno e dicono di fare e le loro emozioni, e tralasciare le proprie concezioni.

### Need vs soluzioni

Sono le necessità, i bisogni.

Partire già con delle soluzioni limita la possibilità di innovare.

## Tecniche di need finding

* interviste: a utenti specifici, agli extreme user, agli esperti…
* questionari
* diario
* pager studies
* camera studies

### Interviste

Sono informali, economiche, permettono di approfondire dando la possibilità di **spaziare**.

Di contro sono soggettive e portano via diverso tempo.

Tipicamente si intervistano utenti di un sistema simile o che andranno a usare il sistema; anche utenti non ideali vanno bene, poiché tutti hanno sempre qualcosa da dire.

#### Come svolgere le interviste

Preparare delle domande, avere qualcuno che prende appunti (o registrare l'intervista), essere curiosi e approfondire ciò che l'utente dice, rimanere neutrali alle risposte date dall'utente.

#### Quali domande evitare

* le domande scontate: meglio chiedere perché
* quelle che contengono la risposta: domande aperte
* quelle troppo generiche
* quelle che chiedono all'utente di sostituirsi al designer
* quelle basate su scenari ipotetici: la realtà deve essere nota all'intervistato
* **quelle che chiedono quanto spesso fai qualcosa**: meglio indicare esattamente quando e non lontano nel tempo (es. "ieri hai mangiato la pastasciutta" è meglio di chiedere "ogni quanto mangi la pastasciutta")

Le interviste possono essere fatte anche:

* lead user: utenti che hanno dei need nuovi, e sono in generale "sofisticati"
* extreme user: utenti che spingono un sistema all'estremo e trovano dei problemi che normalmente la maggior parte degli utenti non trova
* esperti: specialisti del settore, ovviamente la loro esperienza è un plus

Esistono altre due tecniche molto usate: il **laddering** (chiedere sempre perché) e **intercepts** (una domanda sola).

### Questionari

Simili alle interviste, ma le domande sono uguali per tutti gli utenti e molte risposte vengono raccolte subito.

Ci sono diversi tipi di domande: aperte, chiuse, risposta singola ecc

Sono meno flessibili delle interviste ma hanno il vantaggio che sono più condivisibili e si possono raccogliere più dati in più breve tempo.

### Diario

Il diario raccoglie informazioni su attività sporadiche, ma l'utente deve ricordarsi di compilarlo.

### Pager

Molto simile al diario, ma chiedi all'intervistato di fermarsi e prendere nota in tempo reale in momenti particolari della giornata o quando itera un comporamento

### Camera studies

Vengono registrate le interazioni dell'utente.

## Storyboard

Una volta che i need sono stati individuati, dobbiamo identificare le sotto-attività che l'utente può svolgere per soddisfare i need.

Non stiamo progettando le schermate, dobbiamo astrarre i task con dei disegni.

## Prototyping

Abbozzare l'interfaccia del prodotto finale, immaginando le interazioni degli utenti. L'importante è che sia comprensibile e facile da usare.

Bisogna poi testarla per verificare questi due aspetti.

### Approcci dei prototipi

Gli approcci sono tre:

1. Throw away: una volta fatto un prototipo, si capisce cosa non va e si scarta
2. Incrementale: le varie funzioni vengono aggiunte ad ogni revisione
3. Evolutivo: un prototipo serve come base per il successivo che lo migliora

### Low Fidelity vs. High Fidelity

Esistono due tipi di rappresentazioni:

* hi-fidelity: tutti gli elementi sono molto dettagliati; bello perché la navigazione è fluida, ma basta che una cosa non sia al suo posto che l'attenzione dell'utente viene catturata da questa cosa, mentre noi stiamo cercando di capire se il prototipo è utilizzabile e va bene per risolvere i task; il loro comportamento conta di più.
* low-fidelity: tutti gli elementi sono abbozzati, e l'utente capisce di più che non è una rappresentazione accurata della realtà, è più invogliato a fare commenti

### Paper Prototyping

La rappresentazione del prototipo è di tipo low-fidelity su carta, in modo tale che in caso di errori si può buttare e rifare rapidamente.

Non ci si cura dell'estetica.

Si può fare su tool automatici ma poi c'è il rischio che sembra vero e richiede parecchia attenzione a tutti i particolari.

**Un wireframe** è sbagliato, poiché è una rappresentazione high-fidelity.

**Disegnare a lavagne** è sbagliato, dobbiamo testare sugli utenti.

### Il mago di Oz

Interfaccia che simula il comportamento umano, aiutato da un Wizard (un umano) che è nascosto e fornisce input traducendo l'input dell'utente.

Ad esempio inserire un testo o passare alla schermata successiva.

Viene usata soprattutto per UI di dialogo naturale.

Gli svantaggi è che non solo può essere inappropriato in alcune situazioni, ma fare il wizard è faticoso (richiede allenamento) e la tecnologia simulata potrebbe non esistere mai.

### Administrator e observer

Le due figure fondamentali mentre si prototipa o mentre si fanno interviste sono due: administrator e observer.

Il primo è "il padrone" dell'intervista: decide che domande fare, incuriosisce l'utente e chiede lui perché, e in generale è lui a condurre l'intervista.

L'observer si limita a prendere appunti e osservare ciò che l'utente fa, come risponde o quali sono i suoi problemi.

Tuttavia, nel paper prototyping, esiste anche una terza figura che si chiama "human computer" che ha il compito di girare i fogli e presentare le schermate di carta giuste.

## Metodi osservazionali (Evaluation)

Richiedono degli scenari, e si usano per testare l'usabilità e le funzionalità di un sistema e identificare problemi specifici.

Possono essere fatti sia in laboratorio che in collaborazione con gli utenti.

Questi ultimi devono essere degli utenti teorici del sistema e competenti con la realtà di riferimento, con esperienze simili tra loro (es. un gruppo di amici) e massimo 5.

Si descrivono gli scenari e si individuano i task; a ciascuna persona si richiede di svolgere ogni task.

I principali metodi utilizzati sono:

* think aloud: l'utente spiega e pensa ad alta voce cosa sta facendo e cosa crede stia accadendo. è un'operazione semplice e che fa capire cosa ha capito l'utente, ma è soggettivo e il fatto di chiedere di descrivere ad alta voce potrebbe non far sentire libero l'utente di fare quello che vuole
* cooperative eval: l'utente collabora con l'esaminatore, si fanno domande a vicenda. è più user-friendly.
* protocol analysis: si registra una sessione
* post-task walkthrough: si fa un trascript e si chiede all'utente di perché certe affermazioni o comportamenti

### Test in laboratorio vs su campo

In laboratorio si hanno strumenti specifici e un ambiente senza distrazioni, ma perdiamo il contesto e abbiamo difficoltà a vedere gli utenti che collaborano insieme.

Sul campo, abbiamo un ambiente naturale e non abbiamo perdita di contesto. Abbiamo però distrazioni e rumori.

### Esperimenti

Si fa un ipotesi di ciò che deve essere testato, si prendono più gruppi di utenti cambiando una sola variabile e si misurano i risultati.

### Variabili dipendenti vs indipendenti

Le variabili sono cose che andrai a modificare e misurare.

Possono essere di due tipi:

* indipendenti: caratteristiche cambiate per produrre condizioni differenti
  * cambio di interfaccia, numero di elementi in un menù...
* dipendenti: caratteristiche misurate negli esperimenti
  * tempo impiegato, numero di errori

Quando si fa questo tipo di test **bisogna cambiare una variabile indipendente alla volta**.

### Le ipotesi

Un ipotesi è un'idea provvisoria il cui valore deve essere accertato.

### Condizioni

Una **condizione di controllo** è il sistema "normale" per come l'avevamo pensato. Una **condizione sperimentale** è una variabile indipendente che viene modificata rispetto ad una condizione di controllo.

### Metodo sperimentale: between subjects vs within subjects

Il metodo nel quale i soggetti testano le modifiche è detto metodo sperimentale. Ne esistono di due tipi:

**Within subjects**: a ogni partecipante viene assegnata una sola delle condizioni, e svolge il test una volta sola. Richiede più partecipanti, ma gli utenti non risentono del "dover riapprendere".

**Between subjects**: come il within, ma all'utente vengono assegnate tutte le condizioni, quindi esegue il test più volte. Richiede meno partecipanti che però risentono il bisogno del "dover riapprendere".

Per evitare che gli utenti risentano del dover riapprendere si usa **A/B testing**, nel quale una metà degli utenti testa prima la condizione di controllo e poi quella sperimentale e viceversa.

### Expert-based

Vengono fatti durante lo sviluppo.

Ne esistono un walkthrough e tre evaluation: cognitive, heuristic, model-based e review-based evaluation. **(CHMR)**

Nel **cognitive** tipicamente vengono coinvolti specialisti di psicologia cognitiva e rispondono alla domanda "quanto per un utente è semplice imparare a fare quel task".

L'esperto risponde a queste domande:

* l’effetto dell’azione è lo stesso dell’obiettivo dell’utente?
* l’utente può vedere che l’azione è disponibile?
* l’utente capirà che quella è l’azione da eseguire?
* dopo averla eseguita, capirà il feedback ricevuto?

Nell'**heuristic** si usano i **dieci principi proposti da Nielsen** e si vede quanto il progetto viola questi principi.

I dieci principi di Nielsen sono delle **linee guida**, come ad esempio, non nascondere mai l'interfaccia, riconosci piuttosto che ricorda, KISS (keep it short and simple, in pratica "fai le cose senza fronzoli, semplici"), documenta.

Nel **model-based** si rapporta ciò che si vede a dei modelli già esistenti (es. GOMS modello di previsione delle performance dell’utente con un’interfaccia)

Nel **review** ci si basa anche su studi già fatti e consolidati da esperti sugli argomenti discussi.

## Design vs. Designer

Il **design** raggiunge obiettivi settando vincoli e arrivando a compromessi: cosa usiamo, quanto costa, quanto tempo, quali standard...

**Golden rule:** understand your materials e mettere l'utente al primo posto

è importante conoscere gli utenti e il goal è avere un sistema che sia il massimo dell'usabilità

Il **designer** sceglie i materiali e le tecniche, sperimenta e tiene conto dei costi e della componente psicologica. p un progettista che compie scelte razionali e oggettive.

## Waterfall è il male.

**WATERFALL è il male**: se sei un designer non sei mai fermo in un certo punto del waterfall, perché innovi, crei e cambi continuamente.

## Focus vs. Locus

Focus è la volontà di focalizzare l'attenzione su qualcosa e rappresenta un elemento di una interfaccia attivo in un dato istante.

Locus è un'attenzione attratta da qualcosa e può non coincidere con il focus.

Non possiamo controllarla completamente.

**Possiamo concentrarci su una sola cosa alla volta** e se facciamo il contrario abbiamo un rendimento pessimo in tutte le azioni che eseguiamo.

### Compiti automatici

I compiti **automatici** sono quelli che eseguiamo senza pensiero cosciente, ad esempio, camminare mangiando e pensando alla soluzione di un problema di matematica.

### Abitudini

Compiti effettuati ripetutamente, creano un'abitudine positiva che permette di eseguirli senza pensarci. È molto difficile rompere un'abitudine.

**Creo delle abitudini** usando delle **interfacce**.

L'interfaccia dovrebbe permettere la concentrazione su uno specifico task.

### Cambio di contesto

Succede quando si riapre un applicazione da zero o si prepara il prossimo compito da eseguire. In generale richiede circa una decina di secondi.

Si vogliono evitare i cambi di contesto: dopo aver terminato un task, è meglio iniziarne un altro o tornare all'ultimo task interrotto.

## Modi

Dato un gesto, un'interfaccia è in un modo se l'interpretazione di quel gesto è sempre la stessa (es. swipe left da angolo schermo su android significa "indietro").

Quando il gesto viene interpretato in maniera diversa, l'interfaccia si trova in un altro modo.

Es. bottone per attivare o disattivare la sveglia o il tasto caps lock

**Evitare i modi come la peste, e se proprio non puoi farne almeno, allora fa in modo che sei esplicito e ogni comando sia unico per ogni modalità**

Def: un'interfaccia è modale rispetto a un gesto quando lo stato corrente dell'interfaccia non è il luogo dell'attenzione dell'utente e l'interfaccia risponderà al gesto con una tra n possibili risposte, a seconda dello stato

### Quasi-modo

Modo temporaneo: esempio, tenendo premuto il tasto MAIUSC.

### Noun-verb vs. verb-noun

Eseguire azioni (verb) su oggetti (noun).

Noun-verb: si seleziona prima l'oggetto. L'attenzione dell'utente è ridotta e non si verificano errori di modo.

Verb-noun: si seleziona prima l'azione. **CREA UN MODO**

## Le app

### Productivity vs. Utility vs. Immersive

Productivity: svolgi compiti basati sulla manipolazione di informazioni dettagliate. Es. mail o galleria. I dati sono gerarchici.

Utility: visualizzi delle informazioni, l'input è minimo. Es. meteo o livella

Immersive: giochi, sono tutte quelle app che richiedono l'attenzione 100% dell'utente
