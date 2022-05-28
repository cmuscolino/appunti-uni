# 🌐 LTW

## Concetti introduttivi definizioni

**URL**: è uno **standard del web** e **l'identificatore di una risorsa** Si compone da nome del protocollo, nome del dominio e dominio.

**DNS** = nomi simbolici dei computer nella rete Internet

Il DNS gestisce uno spazio di nomi all'interno di una **struttura ad albero**:

* i livello: i soliti .com .net .edu .mil .gov e .int e quelli "nazionali" .uk, .it ecc
* ii livello: ibm.com
  * ogni dominio di secondo livello viene gestito da quelli di primo livello
* iii livello e oltre: sono gestiti dal secondo livello ecc

In passato ci sono state delle "guerre" per i domini perché l'accesso a Internet era ristretto. Il **nameserver** è un programmino che **mappa** il nome di dominio su indirizzo ip.

**Ipertesto**: dal nome stesso, un **documento** che **contiene anche cose diverse** dal testo/immagine, per esempio dei link.

## HTML

L'HTML è l'acronimo di HyperText Markup Language, nasce agli inizi degli anni 90 (1989) da Tim Berners Lee e si contraddistingue per le "marcature".

Fino al 99 ci sono state 4 versioni, ma poi per 15 anni è rimasto fermo. Nel 2014 nacque HTML5 e quindi si ridefinì un nuovo linguaggio, grazie anche ai dispositivi mobili (telefoni e tablet) che via via presero sempre più piede.

### Sintassi

Documento HTML, cioè un testo in un qualsiasi set di caratteri, che contiene:

* **blocchi di testo**
* **tag** ("marcature" o comandi): testo delimitato dai simboli '<' e '>'. es. `<html>`
  * si distinguono due tipi di tag:
    * apertura `<html>`
    * chiusura `</html>`
  * possono contenere **attributi** solitamente nel formato `attributo=valore`,
    * ad esempio: `<img src="ciao.jpg" align="left">` il tag img ha due attributi

Gli **elementi** in HTML sono tutti i blocchi che sono formati da:

* tag di **apertura**
* **corpo**
* tag di **chiusura**

Gli **elementi vuoti** sono tutti quegli elementi che non hanno bisogno di essere chiusi. Si possono avere elementi **nested** ossia l'annidamento di tag in altri tag. I tag **possono essere** scritti anche in maiuscolo --> sono quindi case-insensitive

La semantica dell'HTML **non è stata standardizzata da nessuna parte**: quando scrivo il tag img scrivo che "voglio mettere lì un'immagine" ma ecco spiegato il motivo per il quale ci sono problemi di interpretazione cross-browser.
