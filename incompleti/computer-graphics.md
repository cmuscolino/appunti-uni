---
description: Appunti del corso di Computer Graphics.
---

# 🌈 Computer Graphics

## Introduzione al corso

### Capacità dei sensori

Esistono algoritmi in grado di migliorare la qualità di quello che viene catturato, ossia migliorare la capacità del sensore.

### HDR e bitmap

Fa una serie di foto e fonde quelle immagini.

Ogni carattere sullo schermo sono immagini che vengono convertiti in pixel. Tutto quello che si vede su uno schermo sono **bitmap**, matrici di pixel.

### Raster

Processo di conversione da curve a pixel

### **Differenza tra 2D e 3D**

Gli algoritmi 2D **non** possono essere usati per gli oggetti in 3D, poiché hanno esigenze diverse dovendo, quelli 3D lavorare in 3 dimensioni.

La grafica 3D si idivide in:

* designer CAD
* modellazione

I due mondi sono **indipendenti** tra loro.

### **Scultura digitale**

Oggetti che rappresentano la realtà e sembrano siano stati fatti con la creta.

Esistono due tipi di rendering:

* **molto fedele**: alla realtà nella più alta qualità possibile
* **real time**: lo schermo renderizza "cose" a 1/60s

### **Tricromia**

**L'uomo è tricromatico**; il **colore** è la percezione di un certa onda elettromagnetica

## Ripasso di matematica

### Punti

Posizioni nello spazio 3D

### Vettori

Hanno direzione, verso e intensità (magnitude) e possono essere ovunque all'interno di un certo spazio.

La maggioranza dei software grafici usano una struct di 3 float.

Un sistema di riferimento ha un origine e tre assi di riferimento: F = {x,y,z,o} dove o è l'origine.

### Ortogonale, normale e perpendicolare

Sono tutti e tre la stessa cosa!

## **Immagini**

### Come si rappresenta un'immagine

Distribuzione di valori del piano 3d in uno spazio di colore, una sorta di mappa che associa ad ogni punto un colore.

Le immagini possono essere rappresnetate in diversi modi:

* matrici (che però non si usano mai)
* **array unico**

Si usano 8 bit per rappresentare un pixel. L'8 è destinato a cambiare.

## **Tecnologie di rappresentazione**

* CRT
* LED
* LCD
* OLED
* Plasma

### **CRT**

* **Bianco e nero**: accendi e spegne le celle e avevi risolto il problema. C'è un fascio di elettroni che colpisce il fosforo e questi atomi di fosforo si illuminano.
* **A colori**: faccio partire tre raggi e metto una griglia per guidarli
* **Scanline**: righe che il pennello disegna quando fa il refresh dello schermo

### **LCD**

Duplichiamo le cellette e mettiamoci dei filtrini

### **HDR vs. LDR**

* HDR **=** High Dynamic Range
* LDR = Low Dynamic Range

In realtà questa notazione è altamente imprecisa perché misura il contrasto non l'effettivo intervallo di rappresentazione.

Storicamente le **immagini HDR misurano l'illuminazione**. Adesso siamo in una fase di transizione, con la prevalenza di display HDR in generale, vengono catturati più di 8 bit e la capacità tipicamente è **12 bit**.

I sensori digitali non sono in grado di rappresentare quel range di illuminazione.

Per ricostruire un'immagine HDR si può ricorrere alla **tecnica fusion**: vengono fatte tante foto, ognuna fatta con diverse esposizioni. Una macchina fotografica digitale è in grado di rappresentare bene un'illuminazione in un range finito. **Sopra al massimo è satura, sotto il minimo non c'è abbastanza luce**. Posso prendere allora le parti migliori dalle varie immagini. Questo compito è assegnato agli **algoritmi di processing**.

i) dato un range di valori, rimappalo tra 0 e 1

ii) applico una curva che fa encoding non lineare, prendere il valore di illuminazione e elevarlo a potenza di 2

### ****

## Compositing

Creare un immagine assemblando varie parti di immagini. Es. il green screen

Crossfading = interpolazione lineare --> al variare di un parametro t, a t = 0 ottengo il background, a t=1 il foreground.

Non bastano i colori dell'immagine, ci serve un valore aggiuntivo che stabilisce se un certo pixel è di fg o bg --> Alpha Channel.

Alpha è una frazione.

**Independing coverage**: l'orientamento che hanno quei pixel tra un'immagine e l'altro è indipendente l'uno dall'altro.

### Operatore over (alpha compositing)

Operatore che ci permette di fare "A over B", composizione di immagini

**Formula operatore di compositing (over) a due**: colore di A \* area ricoperta da A + colore di B \* l'area ricoperta da B (esclusa l'area ricoperta da A)

Inventato da Porter & Duff nel 1984

## Materiali

Ci sono diversi modelli di materiali, utilizziamo tre classi principali:

1. **Matte** --> pastello, carta, stucco, non hanno riflessi
   * mi basta descrivere il colore della superficie: mi bastano due valori, una per il colore e una per la texture.
2. **Metalli** --> superfici riflettenti (se quella superficie è levigata si vedono tutti gli oggetti intorno)
   * colore, valore che controlla quanta riflessione è specchio o è "blur"
3. **plastiche** (polish) --> combinazione di matte (base) ricoperte di materiale trasparente
   * colore, quanto è nitida la riflessione

Le texture sono delle immagini da applicare sopra i materiali.

Per ogni punto sulla superficie, ho un corrispondente punto nell'immagine dal quale posso andare a copiare il colore.

Per fare questa cosa, posso usare una funzione che dato un punto su una superficie mi dice le coordinate sull'immagine: il **mapping**.

**UV Mapping:** associa ai vertici dei triangoli un corrispondente punto dell'immagine.

La luce non è altro che associare ad una geometria un canale che emette colore.

C'è un altro modo di fare Texture Mapping: Ptex, usato per la prima volta da Disney. Anziché mappare ogni singolo punto, usa sempre la stessa texture per ogni oggetto e lo fa variare.

Riguardo il **realismo** delle texture, ci sono diversi livelli di realismo e le texture si possono "abbellire" rendendo il materiale "non costante".

Ad esempio: un parquet --> se ci appiccico al materiale un immagine di un parquet, tutti i tasselli sono piatti. Se invece creo un dislivello in ogni tassello, creo più realismo.

Per applicare una texture su un solido possiamo immaginarci **un foglio di carta che avvolge un solido e viene quindi "spalmato" sull'oggetto**. I tagli vengono fatti manualmente tipicamente, sebbene ci siano dei modi per "tagliare" usando software.

C'è un cambiamento di area dal 2D al 3D: ci sono delle **distorsioni di angolo**: o introduco più tagli, o distorgo l'area.

### **Environment maps**

Lavoro su approssimazione: tutto quello vicino a me è accurato, quello lontano non lo renderizzo e ci appiccico un'immagine.

## I triangoli e le forme

Come scegliamo la rappresentazione?

Nei modelli virtuali abbiamo scelta sul modello matematico da usare.

Le varie rappresentazioni matematiche usate per rappresentare una cosa devono avere caratteristiche simili.

Voglio basare i miei algoritmi su una rappresentazione o su molteplici? Un modello che rappresenta bene macchine, magari rappresenta male degli alberi. **Due rappresentazioni matematiche diverse richiedono due interfacce utente diverse**, motivo per cui la grafica adotta poche rappresentazioni semplici da usare per fare più cose --> combinazioni di punti, linee e triangoli.

**Punti:** oggetti geometrici ben definiti dai soli **parametri di posizione**

* non hanno una dimensione
* utili per rappresentare oggetti simil puntali (es. la polvere non la rappresento come singola sfera ma come una serie di punti)

**Linee:** definite tra due punti, utili a rappresentare collezioni di fili (es. capelli, peli, ecc)

**Triangoli:** servono per rappresentare superfici definite da 3 vertici

### **Curse of Dimensionality**

Tre dimensioni devono allocare n^3 dati di dimensione

* la complessità cresce esponenzialmente
* poche rappresentazioni dei volumi <--> invece molte rappresentazioni della sola superficie

### I triangoli perchè?

3 vertici sullo stesso piano --> Normale: vettore ortogonale al piano su cui sta il triangolo proprietà utile: esprimere un punto in un triangolo come media pesata dei suoi vertici (**coordinate baricentriche**)

### Coordinate baricentriche

Comprese tra 0 e 1, la loro somma da 1, sono le **aree dei triangoli generati diviso l'area generica del triangolo.**

Se la loro somma è 1 posso riscrivere la terza come dipendente dalle prime 2 e posso scrivere una funzione che prende 2 soli punti.

Posso scrivere le coordinate baricentriche per punti, per linee, triangoli, tetraedri...

### **Triangle Meshes**

Se ho una superficie posso approssimarla **sfaccettandola** --> perdo la continuità della superficie, ma l'approssimazione è ragionevole; è simile a quello che noi facciamo quando guardiamo elementi reali come griglie di valori.

A seconda della quantità di errore che tollero (la lunghezza media dei lati dei triangoli), uso più o meno triangoli e sono più o meno preciso).

### Texture

Definiamo i **materiali** come **colore dei punti delle superifici** / campo di colori delle superfici.&#x20;

## Raytracing

In grafica ci sono due approcci per il rendering:

* **rasterizzazione**: il contrario di raytracing ()
* **raytracing**: per ogni oggetto della scena, se quell'oggetto può dare colore al pixel calcola l'oggetto

### **Interpolazione**

Memorizzare ai vertici di ogni triangolo un colore.

Applico immagini per variare il colore delle superfici. Per ogni punto della superficie associo un punto dell'immagine.

Sui vertici del triangolo memorizzo le coordinate dell'immagine su ogni vertice. --> riporto i punti del triangolo sul piano dell'immagine.

### Shading

Calcolare l'illuminazione che raggiunge una certa immagine, facendo una qualche simulazione su quel punto su come viene riflessa la luce.

La luce ovviamente quando colpisce un oggetto, va sull'oggetto, altrimenti va su una superficie Le ombre si formano prendendo un punto sulla superficie che vede direttamente la luce. Se invece lungo la linea che connette il punto e la sorgente luminosa, la luce non riesce ad arrivare. Le ombre si formano perché qualcosa è illuminato, qualcosa no.

Un algoritmo di raytracing fa questo: dammi il punto più vicino tra l'oggetto e la luce.

### Emission

Quanta luce emette da solo quell'oggetto --> schematizzato in una costante, basta moltiplicare una costante

**Illuminazione indiretta**: l'algoritmo calcola le ombre in maniera "realistica" simulando la casualità delle ombre L'algoritmo si chiama "Montecarlo" ma se comincio ad approssimare il risultato è molto brutto, l'immagine è pieno di rumore; il problema è che è lento.

### Antialiasing

Invece di calcolarmi il raggio per un solo pixel, prendo un pixel, divido in griglia e lancio 4 8 16 raggi, e faccio la media, in maniera tale che la silhouette di un oggetto non sia "pixelata" ma smooth.



