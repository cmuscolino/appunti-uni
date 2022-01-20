---
description: lunedì 27 settembre 2021
---

# Introduzione

Il SW engineer non è uno sviluppatore. Ha due problemi:

* il cliente non si esprime bene (quindi tradurre i needs dei clienti)
* assegnare le persone a un progetto

Se non funziona qualcosa la colpa è del SE.

Questo problema ha vari aspetti:

* tempo
* budget --> numero di persone

Quindi nel nostro gioco ci sono essenzialmente tre oggetti:

* **environment**: tutto ciò che agisce con l'utente (sistema, utente, sensori...)
* **requisiti**: definiscono tutte le proprietà che il sistema deve rispettare, tipicamente vengono divisi in due classi:
  * funzionali: es. ordinare un vettore
  * non-funzionali: performance es. voglio che per ordinare un vettore impiego 1 microsecondo

Se il sistema lo avessimo potremmo fare infiniti test, ma noi all'inizio non abbiamo il sistema, lo dobbiamo costruire ex-novo.

Inizialmente si costruiscono dei generatori di test e degli **oracoli**, dei programmi che dicono se il test è passato oppure no. Si potrebbero costruire anche dei mockup che approssimano il sistema: se sono un'azienda che faccio sempre lo stesso prodotto (es. chip), potrebbe essere vantaggioso per me fare un mockup usando sempre lo stesso linguaggio.

**La documentazione ha un difetto: si può solo contemplare**: per questo motivo sono nati i test.

Correlazione **oggetto - modello**: in tutti i campi dell'ingegneria si ha presente qual è il SW e qual è il modello. Il SE siccome non ha un risultato tangibile dell'oggetto che andrà a costruire, è difficile da "rappresentare".
