# Magic Score 🧙‍♂️

Segnapunti PWA per **Magic: The Gathering**, ottimizzato per dispositivi mobile.  
Nessuna installazione richiesta — funziona direttamente dal browser e può essere aggiunto alla schermata Home come app nativa.

---

## Funzionalità

### 🃏 Gestione giocatori
- Da **2 a 6 giocatori** simultanei
- Punti vita configurabili: **20 / 30 / 40 / 60 PV**
- Contatori **veleno** (☠ 0–10) e **energia** (⚡ 0–5)
- Colore e icona mana assegnati automaticamente in base al tipo scelto (Bianco, Blu, Nero, Rosso, Verde, Incolore)
- Immagine di sfondo personalizzata per ogni giocatore
- Layout adattivo: verticale su telefono, griglia su tablet/desktop

### 🎲 Dado
- Supporto per **D2, D3, D4, D6, D10, D20, D100**
- Animazione di lancio con risultato in sovraimpressione su ogni carta
- Il risultato più alto e più basso rimangono visibili 2 secondi in più

### ↩ Undo
- Annulla l'ultima modifica ai **punti vita** o al **veleno**
- Storico fino a 40 mosse

### 🏆 Rilevamento vincitore
- Banner automatico quando un solo giocatore è ancora in vita
- Scomparsa automatica al click su **Nuova partita**

### 🔍 Ricerca carte
- Cerca qualsiasi carta MTG per nome
- Risultati multipli con lista selezionabile
- Match esatto → dettaglio diretto
- Mostra: **oracle text** (regole ufficiali), **rulings** Wizards of the Coast, link diretto a **Gatherer**
- Dati forniti da [Scryfall API](https://scryfall.com)

### 💾 Persistenza sessione
- Nome giocatori, punti vita, segnalini e immagini di sfondo vengono **salvati automaticamente**
- Al riavvio dell'app lo stato viene ripristinato esattamente com'era

---

## Installazione come app (PWA)

### iPhone / iPad
1. Apri l'URL in **Safari**
2. Tocca **Condividi** → **Aggiungi a schermata Home**

### Android
1. Apri l'URL in **Chrome**
2. Tocca il menu **⋮** → **Aggiungi a schermata Home**

---

## Sviluppo locale

Il progetto è un singolo file `index.html` — nessuna dipendenza, nessun build step.

```bash
git clone https://github.com/dberillo-droid/Magic-scorekeeper
cd Magic-scorekeeper
# Avvia un server locale (es. con Python)
python -m http.server 3333
# oppure con Node
npx serve .
```

Apri `http://localhost:3333` nel browser.

---

## Tecnologie

- HTML / CSS / JavaScript vanilla — nessun framework
- [Scryfall API](https://scryfall.com/docs/api) per i dati delle carte
- PWA con Service Worker per uso offline
- `localStorage` per la persistenza della sessione

---

## Licenza

MIT
