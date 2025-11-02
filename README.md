# SMPO - Social Media Ostracism Paradigm v3.1 CSV Edition

Paradigma di Ostracismo sui Social Media - Versione italiana v3.1 con gestione profili tramite CSV e sistema di cache busting ottimizzato per esperimenti di ricerca psicologica.

## 🌐 Demo Online
**Sito Live:** [https://villinodippsi.github.io/smpo_itav3_test/](https://villinodippsi.github.io/smpo_itav3_test/)

## 🆕 Novità v3.1 CSV Edition

### Sistema Gestione Profili CSV
La versione 3.1 introduce un **sistema rivoluzionario di gestione profili** che permette di modificare tutti i profili virtuali direttamente da un file Excel/CSV, senza dover modificare codice JavaScript.

**Vantaggi principali:**
- ✅ **Editing semplice**: Modifica profili con Excel, LibreOffice o Google Sheets
- ✅ **No programmazione**: Non serve conoscere JavaScript o JSON
- ✅ **Aggiornamenti rapidi**: Cambia testi, nomi e timing in pochi secondi
- ✅ **Backup automatico**: Versioni precedenti sempre disponibili
- ✅ **Testing facile**: Testa diverse configurazioni senza rischi

### Cache Busting Automatico
Sistema ottimizzato che garantisce il caricamento immediato delle modifiche ai profili:
- ✅ **Nessuna cache del browser**: Ogni ricarica mostra sempre i dati più recenti
- ✅ **Aggiornamenti istantanei**: Modifiche visibili con un semplice F5
- ✅ **Sincronizzazione perfetta**: Script caricati nell'ordine corretto

---

## 📋 Descrizione

Questa versione v3.1 del Social Media Ostracism Paradigm (SMPO) italiano mantiene tutte le funzionalità della v3.0 Addendum (tracking like dati) e aggiunge:

- **Gestione profili tramite CSV**: File Excel per configurare tutti gli 11 profili virtuali
- **Cache busting intelligente**: Sistema che evita problemi di cache del browser
- **Caricamento dinamico ottimizzato**: Script caricati nell'ordine corretto per massima affidabilità

I partecipanti interagiscono con 11 profili virtuali attraverso like permanenti. I ricercatori possono manipolare profili, timing e condizioni sperimentali in modo semplice e immediato.

---

## 🔧 Configurazione Profili con CSV

### File profiles.csv - Gestione Completa dei Profili

Il cuore del sistema v3.1 è il file **`profiles.csv`**, che contiene tutti i profili virtuali in formato tabella.

**Struttura del file:**

| avatar | username | text | likes |
|--------|----------|------|-------|
| avatars/others/01.png | Chiaretta | Ciao sono Chiara, ho 22 anni... | 45000,50000,110000,150000 |
| avatars/others/02.png | George | Sono un ragazzo di 19 anni... | 12000,35000,80000,100000 |

**Campi configurabili:**

1. **avatar** (path immagine)
   - Formato: `avatars/others/NN.png`
   - Esempio: `avatars/others/01.png`
   - Corrisponde al file immagine nella cartella `avatars/others/`

2. **username** (nome utente)
   - Qualsiasi nome, anche con spazi
   - Esempio: `George`, `Chiara R.`, `Anna_95`
   - Massimo ~20 caratteri consigliato

3. **text** (contenuto del post)
   - Descrizione/presentazione del profilo
   - Esempio: `"Ciao sono Chiara, ho 22 anni e studio a Roma..."`
   - Lunghezza consigliata: 100-300 caratteri
   - Nota: Se contiene virgole, racchiudere tra virgolette in Excel

4. **likes** (timing like automatici)
   - Lista di timestamp separati da virgola
   - Formato: millisecondi dall'inizio del task
   - Esempio: `45000,50000,110000,150000`
   - Significa: like a 45s, 50s, 110s, 150s dall'inizio

### Come Modificare i Profili

#### Metodo 1: Excel / LibreOffice Calc (Consigliato)

1. **Apri il file CSV**
   ```
   File → Apri → profiles.csv
   Seleziona delimitatore: virgola
   ```

2. **Modifica i profili**
   - Cambia nomi utente nella colonna B
   - Modifica testi nella colonna C
   - Aggiorna timing like nella colonna D

3. **Salva correttamente**
   ```
   File → Salva con nome
   Formato: CSV (separato da virgola) (.csv)
   Encoding: UTF-8
   ```

#### Metodo 2: Google Sheets

1. **Importa il file**
   ```
   File → Importa → Carica → profiles.csv
   ```

2. **Modifica online**
   - Editing diretto nelle celle
   - Formattazione automatica

3. **Esporta**
   ```
   File → Scarica → Valori separati da virgola (.csv)
   ```

#### Metodo 3: Editor di Testo (Avanzato)

```csv
avatar,username,text,likes
avatars/others/01.png,Chiaretta,"Ciao, sono Chiara!",45000,50000,110000
avatars/others/02.png,George,Sono un ragazzo di 19 anni,12000,35000,80000
```

**⚠️ Attenzione:**
- Usa sempre virgolette `"..."` se il testo contiene virgole
- Mantieni l'encoding UTF-8 per caratteri accentati
- Prima riga (intestazione) deve rimanere invariata

### Esempi Pratici di Modifica

#### Esempio 1: Cambiare un Nome Utente

**Prima:**
```csv
avatars/others/01.png,Chiaretta,"Ciao sono Chiara...",45000,50000
```

**Dopo:**
```csv
avatars/others/01.png,Sofia,"Ciao sono Chiara...",45000,50000
```

#### Esempio 2: Modificare Timing Like

**Prima:**
```csv
avatars/others/02.png,George,"Sono un ragazzo...",45000,50000,110000,150000
```

**Dopo (like più frequenti):**
```csv
avatars/others/02.png,George,"Sono un ragazzo...",30000,40000,50000,60000
```

#### Esempio 3: Cambiare Testo Presentazione

**Prima:**
```csv
avatars/others/03.png,Elodie,"Studio medicina",12000,35000
```

**Dopo:**
```csv
avatars/others/03.png,Elodie,"Sono una studentessa di psicologia con la passione per la ricerca",12000,35000
```

### Aggiornamento Profili sul Sito

Dopo aver modificato `profiles.csv`:

1. **Salva il file** in formato CSV UTF-8
2. **Carica su GitHub** (sostituendo quello esistente)
3. **Ricarica la pagina** del test (F5)
4. ✅ **Le modifiche sono immediate** grazie al cache busting!

**Nota importante:** Non serve cancellare la cache del browser o chiudere le tab. Il sistema di cache busting garantisce che ogni ricarica mostri sempre i dati più recenti.

---

## 🎨 Gestione Avatar

### Struttura Directory Avatar

```
avatars/
├── avatar_0.png          # Avatar selezione partecipante
├── avatar_1.png          
├── ...
├── avatar_11.png         
└── others/               # Avatar profili virtuali
    ├── 01.png           # Corrisponde a avatars/others/01.png nel CSV
    ├── 02.png
    ├── 03.png
    └── ...
```

### Aggiungere/Modificare Avatar

1. **Per profili virtuali:**
   - Crea immagine 250x250px in formato PNG
   - Nome file: numero sequenziale (es: `01.png`, `02.png`)
   - Carica nella cartella `avatars/others/`
   - Nel CSV, usa path: `avatars/others/01.png`

2. **Per selezione partecipanti:**
   - File formato: `avatar_N.png` (N = numero da 0)
   - Dimensione: 250x250px
   - Posizione: cartella `avatars/`
   - Numero totale configurabile in `main.js`: `settings.numberofavatars = 12`

---

## 🚀 Sistema Cache Busting

### Problema Risolto

**Prima della v3.1:**
- Modifiche a `profiles.csv` non visibili immediatamente
- Necessario cancellare cache browser manualmente
- Comportamento inconsistente tra utenti

**Con v3.1:**
- ✅ Ogni ricarica scarica sempre la versione più recente
- ✅ Cache browser bypassata automaticamente
- ✅ Nessuna azione manuale richiesta

### Come Funziona

Il sistema aggiunge un **timestamp univoco** all'URL del file CSV:

```javascript
// Timestamp generato ad ogni caricamento pagina
var timestamp = new Date().getTime();
var csvUrl = 'profiles.csv?v=' + timestamp;

// Esempio risultato:
// profiles.csv?v=1699023456789
// profiles.csv?v=1699023567890 (alla ricarica successiva)
```

**Risultato:**
- Il browser vede URL diversi ad ogni ricarica
- Scarica sempre il file fresco da GitHub
- Modifiche visibili immediatamente con F5

### Ordine di Caricamento Ottimizzato

Gli script vengono caricati nell'ordine corretto per garantire funzionamento affidabile:

```html
1. profiles.json (loader CSV con cache busting)
   ↓ [ASPETTA completamento]
2. main.js (script principale)
   ↓ [Trova window.others già pronto]
3. ✅ Applicazione funzionante
```

---

## 🔧 Configurazione Rapida

### 1. Setup Iniziale

**File necessari:**
- `index.html` - Pagina principale (con cache busting integrato)
- `profiles.json` - Loader CSV automatico
- `profiles.csv` - Dati profili (modificabile con Excel)
- `main.js` - Logica esperimento
- `style.css` - Stili interfaccia

### 2. Configurazioni Condizioni Sperimentali

**Nel file main.js - funzione set_settings():**

```javascript
function set_settings() {
    // Durata task
    settings.tasklength = 180000; // 3 minuti
    
    // Avatar disponibili per selezione utente
    settings.numberofavatars = 12;
    
    // Condizione 1: Ostracismo (1 like ricevuto)
    settings.condition_1_likes = [12000, 9999999];
    
    // Condizione 2: Inclusione (6 like ricevuti)  
    settings.condition_2_likes = [10000, 15000, 35000, 80000, 132000, 150000];
    
    // Condizione 3: Sovrainclusione (9 like ricevuti)
    settings.condition_3_likes = [10000, 11000, 15000, 35000, 80000, 100000, 110000, 150000, 20000];
}
```

### 3. Parametri URL per Condizioni

**Formato standard:**
```
https://villinodippsi.github.io/smpo_itav3_test/?c=N&p=ID&redirect=URL
```

**Parametri:**
- `c`: Condizione (1, 2, 3)
- `p`: ID partecipante (formato 001, 002, ...)
- `redirect`: URL questionario codificato

**Esempi:**
```
Condizione 1: ?c=1&p=001&redirect=https%3A//questionario.com
Condizione 2: ?c=2&p=002&redirect=https%3A//questionario.com
Condizione 3: ?c=3&p=003&redirect=https%3A//questionario.com
```

---

## 📊 Dati Esportati

### Parametri Base
- `p`: ID partecipante
- `c`: Condizione assegnata (1-3)
- `u`: Username inserito
- `av`: Numero avatar selezionato
- `d`: Descrizione personale

### Parametri Like Tracking (v3.0+)
- `total_likes`: Numero like dati totali
- `liked_usernames`: Lista CSV utenti che hanno ricevuto like
- `liked_avatars`: Lista CSV avatar che hanno ricevuto like
- `like_times`: Lista CSV timestamp like (ms dall'inizio task)

**Esempio URL finale generato:**
```
questionario.com?p=001&c=2&u=TestUser&av=5&d=Descrizione&total_likes=5&liked_usernames=Sarah,John,George&liked_avatars=other_05,other_03,other_04&like_times=15000,32000,45000
```

---

## 📁 Struttura File

```
smpo_itav3_test/
├── index.html              # Pagina principale (con cache busting)
├── main.js                 # Logica test e condizioni
├── profiles.json           # Loader CSV automatico
├── profiles.csv            # ⭐ PROFILI MODIFICABILI CON EXCEL
├── style.css               # Stili interfaccia
├── shortcut.js             # Script supporto
├── avatars/
│   ├── avatar_0.png       # Avatar selezione partecipante
│   ├── ...
│   ├── avatar_11.png
│   └── others/            # Avatar profili virtuali
│       ├── 01.png         # Corrispondono ai path nel CSV
│       ├── 02.png
│       └── ...
└── docs/                  # Documentazione
    └── esempi/
```

---

## 🎯 Workflow Ricercatore

### Setup Esperimento

1. **Configura profili virtuali**
   - Apri `profiles.csv` con Excel
   - Modifica nomi, testi, timing
   - Salva in UTF-8

2. **Carica su GitHub**
   - Upload `profiles.csv` aggiornato
   - Commit delle modifiche

3. **Test immediato**
   - Apri URL test
   - Ricarica (F5) per vedere modifiche
   - ✅ Profili aggiornati visibili subito

### Durante Raccolta Dati

1. **Genera link partecipanti**
   ```
   https://villinodippsi.github.io/smpo_itav3_test/?c=1&p=001&redirect=SURVEY_URL
   https://villinodippsi.github.io/smpo_itav3_test/?c=2&p=002&redirect=SURVEY_URL
   https://villinodippsi.github.io/smpo_itav3_test/?c=3&p=003&redirect=SURVEY_URL
   ```

2. **Distribuisci ai partecipanti**
   - Link unici per ogni partecipante
   - Condizione bilanciata automaticamente

3. **Raccogli dati**
   - Parametri automaticamente passati al questionario
   - Tracking like completo

---

## 🔍 Troubleshooting

### Problema: Modifiche CSV non Visibili

**Causa:** File non aggiornato su GitHub o cache browser residua

**Soluzione:**
```
1. Verifica upload CSV su GitHub completato
2. Hard reload: Ctrl+Shift+R (Windows) o Cmd+Shift+R (Mac)
3. Console (F12): verifica messaggio "✅ Profili caricati da CSV"
4. Se persiste: modalità incognito per test pulito
```

### Problema: Errore Parsing CSV

**Causa:** Formato file non corretto

**Soluzione:**
```
1. Apri CSV con editor testo
2. Verifica encoding UTF-8
3. Controlla virgolette per testi con virgole
4. Verifica intestazione corretta (avatar,username,text,likes)
```

### Problema: Avatar Non Visualizzati

**Causa:** Path non corretto nel CSV

**Soluzione:**
```
1. Verifica path nel CSV: avatars/others/01.png
2. Controlla file esista effettivamente nella cartella
3. Naming: numeri con zero padding (01.png, non 1.png)
```

---

## 📚 Riferimenti

**Base teorica:**
> Wolf, W., Levordashka, A., Ruff, J. R., Kraaijeveld, S., Lueckmann, J.-M., & Williams, K. D. (2014). Ostracism Online: A social media ostracism paradigm. *Behavior Research Methods*, 47(4), 973-991.

**Ottimizzazioni tecniche v3.1:**
- Sistema CSV parsing client-side con XMLHttpRequest sincrono
- Cache busting automatico con timestamp query parameters
- Ordine caricamento script ottimizzato tramite onload callbacks

---

## 🎓 Credits

**Sviluppo v3.1 CSV Edition:**
- Sistema gestione profili CSV
- Cache busting automatico
- Ottimizzazioni caricamento

**Versione base SMPO italiano:**
- Adattamento paradigma originale Wolf et al. (2014)
- Implementazione tracking like (v3.0 Addendum)

---

## 📝 Changelog

### v3.1 CSV Edition (Novembre 2025)
- ➕ Sistema gestione profili tramite CSV
- ➕ Cache busting automatico per aggiornamenti istantanei
- ➕ Caricamento script ottimizzato con onload callbacks
- ➕ Editing profili con Excel/Google Sheets
- 🔧 Risolti problemi cache browser
- 🔧 Migliorata affidabilità caricamento dati

### v3.0 Addendum (Agosto 2025)
- ➕ Sistema tracking like dati
- ➕ Esportazione parametri comportamentali
- ➕ Feedback visivo animato

### v3.0 Base
- Versione italiana SMPO
- 3 condizioni sperimentali
- Interfaccia social media simulata

---

*Versione 3.1 CSV Edition - Novembre 2025*  
*Per supporto: emiliano.pes@uniroma1.it*Riprova
