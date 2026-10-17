# Scheda Palestra

Sito per compilare la programmazione di forza e pliometrie (pallavolo).

- Login con il solo nome: ognuno ritrova i propri dati scrivendo lo stesso nome.
- **Giorno 1** – Forza, **Giorno 2** – Pliometrie.
- Per ogni esercizio, tabella S1–S8 con RIP, PESO e RPE modificabili. Le caselle "/" non si compilano.
- Salvataggio automatico.

## Salvataggio dei dati

- **Senza Firebase** (`firebase-config.js` con `null`): i dati restano nel browser del dispositivo. I pulsanti *Backup* / *Ripristina* servono a spostarli.
- **Con Firebase**: i dati vengono salvati su Firestore e si ritrovano da qualsiasi dispositivo. Una copia locale permette di usarlo anche senza rete.

### Attivare Firebase

1. Vai su <https://console.firebase.google.com> e crea un progetto (Google Analytics non serve).
2. *Build → Firestore Database → Crea database*, scegli la località `eur3 (europe)` e avvia in *modalità produzione*.
3. Nella scheda *Regole* incolla il contenuto di `firestore.rules` e pubblica.
4. *Impostazioni progetto → Le tue app → icona Web `</>`*: registra l'app e copia l'oggetto `firebaseConfig`.
5. Incollalo in `firebase-config.js` al posto di `null` (`window.FIREBASE_CONFIG = { ... };`) e fai commit.

La chiave `apiKey` di Firebase non è segreta: è normale che sia nel codice pubblico. L'accesso ai dati è controllato dalle regole.

**Attenzione:** il login è solo il nome, quindi chiunque conosca il nome di un'altra persona può aprirne la scheda. Va bene per un gruppo di squadra, non per dati riservati.

## Modificare gli esercizi

Il programma si trova nella costante `PROGRAMMA` dentro `index.html`.
