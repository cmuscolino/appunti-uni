# Processi di modellizzazione

Processi software --> insieme di attività

* specifiche - cosa fa
* design / implementazione - organizzazione del sistema
* validation - prova che faccia quanto richiesto
* evoluzione - migliorare il processo in base ai need

Software process model = rappresentazione astratta di un problema

### Processi produttivi

Esistono due tipo di processi produttivi:

1. **Plan Driven**: faccio un piano e lo seguo, comodo misurare il progetto rispetto al piano
2. **Agile Driven**:faccio un piano incrementale step by step; planning -> lavoro -> planning -> lavoro -> ... Nella pratica si usa un **ibrido**.

### Modelli di sviluppo

1. **Waterfall** (a cascata): plan driven, le fasi sono tutte ben divise e assegnate
   * **svantaggi**: i requisiti e l'integration li si può vedere solo a distanza di tempo, non sai come cambieranno; **è punitivo**, se devo cambiare qualcosa devo tornare indietro, ed **è sequenziale**: devo eseguire tutte le fasi per forza in un certo ordine
2. **Sviluppo incrementale:** implementa sia agile che plan driven
   * è una specie di waterfall in cui ci sono dei microcicli per lavorare a più riprese su tutto
   * per attivarla serve un prototipo, si fanno versoni intermedie fino alla versine finale
   * **vantaggio:** posso mostrare al cliente la versione intermedia o iniziale e avere un feedback
   * **svantaggio:** il processo e lo stato di avanzamento non sono visibili perché non ho un piano; inoltre senza progetto ci si può perdere nello sviluppo
3. **CI e CD:** il sistema viene assemblato a parti già esistenti; può essere sia plan driven che agile

### Reuse oriented sw engineering

Meno costi e rischi dato che riutilizzo cose già sviluppate Velocità di progettazione Non ho controllo sull'eveoluzione dei sistemi --> se il mio fornitore non produce più aggiornamenti per quel sistema mi attacco Il testing occupa la maggior parte dei costi di utilizzo + design e sviluppo
