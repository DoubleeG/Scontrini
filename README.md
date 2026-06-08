# ScontrinoSmart

ScontrinoSmart è una web app per organizzare gli scontrini della spesa, salvare i prodotti acquistati, confrontare i prezzi nel tempo e gestire una lista della spesa personale.

Il progetto è stato realizzato come web app utilizzando **Supabase** per database e autenticazione e **Netlify** per il deploy del frontend. La scelta di questi servizi nasce anche dalla disponibilità di piani gratuiti, utili a mantenere i costi del progetto molto contenuti nelle prime fasi di sviluppo.

## Descrizione
L'app permette a ogni utente di accedere al proprio spazio personale tramite autenticazione e di salvare in modo ordinato i dati dei propri scontrini.

L'obiettivo del progetto è trasformare le informazioni presenti su uno scontrino in dati strutturati, consultabili e modificabili, così da poter monitorare gli acquisti, confrontare i prezzi dei prodotti e semplificare la gestione della spesa.

L'app include anche una schermata introduttiva visibile prima del login, pensata per spiegare in modo immediato le principali funzionalità disponibili e il valore del progetto per l'utente.

## Demo live
La versione online del progetto è disponibile qui:  
[Visita ScontrinoSmart](https://scontrinosmart.netlify.app/)

## Funzionalità principali

### Accesso e presentazione iniziale
- Prima dell'autenticazione, l'app mostra una schermata introduttiva con una breve spiegazione delle principali funzionalità disponibili.
- La schermata iniziale presenta in modo sintetico le aree chiave del progetto: inserimento scontrini, confronto prezzi, prodotti preferiti e lista della spesa.
- Accesso personale per ogni utente.
- Gestione separata dei dati tramite account individuale.

### Inserimento scontrini
- Aggiunta di un nuovo scontrino tramite JSON.
- Presenza di un prompt predefinito da copiare e usare su qualsiasi AI esterna.
- L'utente non carica la foto dello scontrino direttamente nell'app: la foto viene scattata o caricata su un servizio AI esterno, che restituisce un JSON strutturato da copiare e incollare successivamente in ScontrinoSmart.
- Possibilità di inserimento e revisione manuale dei dati.

### Gestione prodotti
- Visualizzazione dei prodotti estratti dagli scontrini.
- Salvataggio di informazioni come nome prodotto, prezzo, prezzo scontato, quantità e prezzo per unità o per kg quando disponibile.
- Assegnazione automatica iniziale delle categorie tramite AI esterna, con possibilità di modifica completa da parte dell'utente.
- Modifica del nome del prodotto e della categoria in qualsiasi momento.

### Modifica scontrino
- Apertura dello scontrino originale associato a un prodotto.
- Modifica di supermercato, data, totale e prodotti contenuti nello scontrino.
- Modifica dei prezzi, delle quantità e di altri dettagli dei prodotti.
- Aggiunta o rimozione manuale di prodotti all'interno dello scontrino.

### Consultazione scontrini
- Visualizzazione dello storico degli scontrini salvati.
- Possibilità di filtrare gli scontrini per anno e mese, per rendere più semplice la consultazione dello storico.

### Analisi prezzi
- Storico degli acquisti per prodotto.
- Confronto dei prezzi registrati nei diversi supermercati.
- Evidenza del prezzo minimo e massimo rilevato.
- Visualizzazione del miglior prezzo disponibile per prodotto.

### Preferiti
- Sezione dedicata ai prodotti preferiti.
- Possibilità di salvare rapidamente i prodotti usati più spesso.

### Lista della spesa
- Creazione di una lista della spesa personalizzata.
- Aggiunta manuale dei prodotti da acquistare.
- Collegamento dei prodotti salvati alla lista della spesa.
- Gestione della quantità e dello stato di completamento degli elementi.
- Suggerimento del supermercato più conveniente per alcuni prodotti presenti nella lista.

### Dashboard iniziale
- Panoramica generale con:
  - numero di scontrini salvati;
  - spesa totale registrata;
  - numero di prodotti unici;
  - numero di supermercati presenti nello storico;
  - elenco degli ultimi scontrini inseriti.

## Flusso di utilizzo
1. L'utente apre l'app e visualizza una breve panoramica delle funzionalità principali.
2. Effettua il login.
3. Apre la sezione per aggiungere un nuovo scontrino.
4. Copia il prompt fornito dall'app.
5. Usa il prompt su un servizio AI esterno di sua scelta.
6. Scatta o carica lì la foto dello scontrino.
7. Ottiene un JSON strutturato.
8. Incolla il JSON nell'app.
9. Controlla, modifica e salva i dati estratti.
10. Consulta i prodotti, confronta i prezzi e aggiorna preferiti o lista della spesa.

## Uso dell'AI
L'app **non integra direttamente un modello AI** tramite API o servizi interni.

L'AI viene utilizzata solo in modo esterno al sistema: l'utente copia un prompt fornito dall'app, lo usa su un servizio AI di sua scelta, carica o fotografa lì lo scontrino e ottiene un JSON da incollare successivamente nell'app.

Questo approccio permette di sfruttare strumenti AI per l'estrazione e la prima strutturazione dei dati, mentre la gestione, il salvataggio e la modifica finale delle informazioni avvengono interamente all'interno dell'app.

## Tecnologie utilizzate
- HTML
- CSS
- JavaScript
- Supabase
- Netlify

## Database
L'app utilizza Supabase come backend per la gestione dei dati e dell'autenticazione.

### Tabelle principali
- `scontrini` → contiene supermercato, data, totale e prodotti associati allo scontrino.
- `preferiti` → memorizza i prodotti preferiti dell'utente.
- `lista_spesa` → salva i prodotti da acquistare, con quantità e stato di completamento.
- `prodotti_categorie` → associa i prodotti alle categorie personalizzate.
- `prodotti_community` → raccoglie informazioni sui prodotti e sui prezzi registrati.

Le tabelle sono collegate all'utente tramite `user_id`, con riferimento al sistema di autenticazione di Supabase.

Una parte importante del progetto è la progettazione del database, pensato per gestire in modo separato utenti, scontrini, prodotti, preferiti e lista della spesa.
  
## Di seguito i dettagli del datatabase utilizzato
![Schema database](./Screenshot/Database.png)

## Stato del progetto
Il progetto è attualmente in continuo aggiornamento e sviluppo.

L'interfaccia, le funzionalità e la struttura dei dati vengono migliorate progressivamente, con l'obiettivo di rendere l'app sempre più utile per la gestione della spesa e l'analisi dei prezzi.

## Nota sullo sviluppo
Questo progetto è stato ideato, costruito e migliorato con il supporto dell'AI.

L'AI è stata utilizzata come strumento di supporto durante lo sviluppo, nella generazione di idee, nel debugging, nella scrittura e revisione di parti del codice e nella definizione di alcune soluzioni implementative.

Le scelte progettuali, l'adattamento delle funzionalità, le modifiche finali e l'organizzazione complessiva del progetto sono state gestite direttamente dall'autore.
