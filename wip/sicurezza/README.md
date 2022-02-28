# 🔒 Sicurezza

## Le ere della sicurezza informatica

Negli **anni 70**: le applicazioni soprattutto **militari**, e la sicurezza era **gestita da specialisti**. Il problema principale erano i **ruoli**: non rendere le informazioni accessibili ai ranghi inferiori / superiori.

Un problema del genere lo riscontriamo ora con le basi di dati: puoi sapere qual è lo stipendio medio dell'ateneo ma non di quello specifico.

Negli **anni 80**: ci sono macchine con **utente unico**. Non c'è bisogno di classificare i dati ecc, tanto c'è una persona sola che gestisce quella macchina e quindi **non c'è bisogno della sicurezza informatica**. Nasce il \[\[modello di Clark-Wilson]] e nascono i worm e i virus.

Negli **anni 90** spunta Internet: nascono i browser, le email ecc il problema è che **le macchine sono esposte**, non si ha protezione né sapere chi ha accesso sui dati. Si sviluppano quindi firewall, SSL, sandbox...

Negli **anni 2000**: spuntano hacker di professione, leggi per incoraggiare la firma elettronica, le app B2C (Amazon, ebay Google...), il contenuto dinamico tipo JS e i meccanismi di chiave pubblica e privata. Si delega la sicurezza gli utenti del proprio pc (o di quello altrui). Innovazioni, passano nelle mani degli utenti, senza porsi il problema della sicurezza.

## Crittografia

Significa **nascondere la scrittura** , rendere illegibili delle informazioni.

### Storia

Ha origine dagli antichi egizi e addirittura Giulio Cesare: infatti famoso è il \[\[Cifrario di Cesare]] Gli arabi sono stati i primi a mettere per iscritto la \[\[crittoanalisi]]: l'analisi del testo cifrato senza avere gli strumenti adatti per decifrarlo.

### Terminologia basilare

* **Encryption** (e decryption): cifratura e decriptazione
* **Plaintext** testo in chiaro

### Algoritmi per la cifratura

Esistono due tipi di algoritmi per cifrare

* **ristretti**: non si sa che algoritmo di cifratura viene usato, **è proprietario**
* **key-based algorithm**: è basata su una chiave e l'algoritmo è noto
  * chiave **simmetrica**: un'**unica** chiave sia per criptare che decriptare
    * una volta che la chiave viene scoperta il sistema è totalmente vulnerabile, e non è particolarmente scalabile perché dobbiamo scambiare un numero enorme di chiavi.
  * chiave **asimmetrica**: **coppia di chiavi**, chiave pubblica e chiave privata

### Cifrari

Stream: cifri un carattere alla volta

Block: blocchi di lunghezza prefissata che vengono cifrati tutti insieme

### Chiave a lungo termine vs. chiave a breve termine

Quelle a **lungo termine** sono quelle "generali" e posso usarle per scambiare chiavi a breve termine. Le chiavi **a breve termine (o di sessione)** invece servono a scambiare tutti gli altri messaggi.

## Crittoanalisi

La crittoanalisi è quell'operazione che permette di decifrare il testo senza avere gli strumenti necessari.

Tipicamente viene svolta per testare la bontà di un algoritmo.

Ci sono diversi tipi di crittoanalisi:

* **ciphertext only**: sa solo il testo cifrato
* **known plaintext**: sa solo alcune coppie di testo cifrato - non cifrato
* **chosen plaintext**: come il known, ma solo casi specifici del testo in chiaro
* **chosen ciphertext**: come il chosen, ma solo casi specifici del testo cifrato

## Tecniche di base per la cifratura

* **Cifrario Monoalfabetico**: solo una lettera shiftata -> Cifrario di Cesare
* **Cifrario polialfabetico**: uso più alfabeti in un certo ordine -> Cifrario di Vigenere
* **Cifrario a permutazione**
* **Product cipher** -> perm + sost + perm + sost -> es. DES

### Cifrario monoalfabetico

**Analisi di frequenza (frequency analysis)**

Per decriptare un testo si usa questa tecnica. Supponendo di avere un testo naturale cifrato

1. Si contano tutte le occorrenze delle singole lettere
2. Si verifica la distribuzione di quelle lettere all'interno della lingua target
3. Si sostituisce la presunta lettera
4. Si deducono le parole possibili (es. se ho XBe in inglese ho poche parole di tre lettere che finiscono con e quindi posso sostituire tutto con 'the') e si continua a sostituire a catena

{% content-ref url="cifrario-di-cesare.md" %}
[cifrario-di-cesare.md](cifrario-di-cesare.md)
{% endcontent-ref %}

### Cifrario polialfabetico

Usi i cifrari a rotazione (es. 213 -> prima usi il secondo cifrario, poi il primo e poi il terzo).

Rende più compatta la distribuzione e rende il testo meno soggetto a known-plaintext attack, perché ovviamente la distribuzione delle lettere è diversa.

Esempo: Cifrario di Vigenere

### Cifrario a permutazione

Plaintext: 1 2 3 4 Cyphert: 4 3 1 2

Una permutazione significa riordinare gli elementi. Più è lungo il testo, più è efficiente la permutazione

Procedimento:

1. CORSODISICUREZZA
2. Dividi in blocchi, diciamo di 4 lettere
3. CORS ODIS ICUR EZZA
4. Applica la chiave: SRCO SIOD RUIC AZEZ

Lo spazio delle chiavi è n!, ed è crackabile con un known-plaintext.

### Product Cipher

Perm + sost + perm + sost es. **DES**

## DES

Nasce nel 1977, chiavi a 56 bit e blocchi di 64. Abolito in funzione del 3DES.

Come un messaggio viene cifrato:

* initial permutation
* left half (untouched)
* right half = right half -> substitution -> transposition -> xor with left half

## Cryptosystem

Quintupla definita da (E, D, M, K, C)

* M insieme dei testi in chiaro
* K insieme delle chiavi
* C insieme dei testi cifrati
* E funzione che cifra (E: M -> C | k app. K)
* D funzione che decifra (D: C -> M | k app. K)
