# 🛠️ SMPO Tools - Utilities per la Gestione del Paradigma

Questa cartella contiene tre strumenti HTML standalone per facilitare la gestione e configurazione del paradigma SMPO (Social Media Ostracism Paradigm).

## 📦 Contenuto

| Tool | File | Descrizione |
|------|------|-------------|
| 🔗 **Participant Manager** | `smpo-participant-manager.html` | Gestione partecipanti e generazione link |
| 📝 **Profile Generator** | `profile-generator-addendum.html` | Creazione e modifica profili avatar |
| ✂️ **Avatar Cutter** | `avatar-cutter.html` | Ritaglio immagini avatar |

---

## 🔗 1. SMPO Participant Manager

### 📋 Cosa fa
Gestisce l'assegnazione dei partecipanti alle condizioni sperimentali e genera automaticamente i link personalizzati per l'esperimento SMPO.

### 🎯 Funzionalità principali
- ✅ Aggiunta partecipanti (manuale o bulk)
- ✅ Assegnazione condizioni (Ostracismo, Inclusione, Sovrainclusione)
- ✅ Codifica automatica URL questionario
- ✅ Generazione link personalizzati
- ✅ Export/Import CSV
- ✅ Auto-bilanciamento condizioni
- ✅ Statistiche in tempo reale

### 🚀 Come usare

#### Setup Iniziale
1. **Apri** `smpo-participant-manager.html` nel browser
2. **Inserisci l'URL del questionario** (es. Qualtrics)
   ```
   https://tuodominio.qualtrics.com/jfe/form/SV_CODICE
   ```
3. **Clicca "🔐 Codifica"** per codificare l'URL automaticamente
4. L'URL codificato apparirà nel campo sottostante

#### Aggiungere Partecipanti

**Metodo 1: Manuale**
1. Compila i campi: Nome, Cognome, Data di Nascita, Sesso
2. Scegli la Condizione (1=Ostracismo, 2=Inclusione, 3=Sovrainclusione)
3. Lascia vuoto l'ID per assegnazione automatica (o inseriscine uno specifico)
4. Clicca "➕ Aggiungi"

**Metodo 2: Generazione Multipla (per test)**
1. Clicca "⚡ Genera Multipli"
2. Inserisci il numero di partecipanti da generare
3. I partecipanti verranno creati con dati casuali

**Metodo 3: Importa CSV**
1. Clicca "📂 Importa CSV"
2. Seleziona un file CSV esistente
3. I partecipanti verranno caricati automaticamente

#### Generare i Link
1. Dopo aver aggiunto i partecipanti, clicca "🔗 Genera/Aggiorna Link"
2. I link verranno generati nel formato:
   ```
   https://villinodippsi.github.io/smpo-socialmedia-ita/index.html?c=1&p=1&redirect=[URL_CODIFICATO]
   ```

#### Esportare il CSV
1. Clicca "📥 Esporta CSV"
2. Il file `partecipanti_smpo_ita.csv` verrà scaricato
3. Usa questo file per gestire l'assegnazione dei partecipanti

#### Funzioni Extra
- **📋 Copia Link**: Copia il link di un singolo partecipante
- **🎯 Auto-Bilancia Condizioni**: Distribuisce equamente le condizioni (1-2-3-1-2-3...)
- **🗑️ Cancella Tutto**: Rimuove tutti i partecipanti

### 📊 Le 3 Condizioni Sperimentali

| Codice | Nome | Descrizione | Numero Likes |
|--------|------|-------------|--------------|
| **c=1** | OSTRACISMO | Il partecipante riceve pochi o nessun like | 0-2 likes |
| **c=2** | INCLUSIONE | Il partecipante riceve un numero normale di like | 6-8 likes |
| **c=3** | SOVRAINCLUSIONE | Il partecipante riceve molti like | 12-15 likes |

### 📁 Formato CSV Generato
```csv
Nome,Cognome,Data_Nascita,Sesso,ID,Condizione,Link_Partecipazione
Marco,Rossi,1995-03-15,M,1,1,"https://villinodippsi.github.io/..."
Giulia,Bianchi,1997-07-22,F,2,2,"https://villinodippsi.github.io/..."
```

---

## 📝 2. Profile Generator (Addendum)

### 📋 Cosa fa
Permette di creare e modificare i profili degli avatar (membri del gruppo) nel file `profiles_v3_addendum.json`.

### 🎯 Funzionalità principali
- ✅ Caricamento file `profiles_v3_addendum.json`
- ✅ Modifica profili esistenti (username, descrizione, avatar path)
- ✅ Gestione likes (timestamp in millisecondi)
- ✅ Upload immagini avatar
- ✅ Generazione file JavaScript compatibile
- ✅ Anteprima JSON in tempo reale

### 🚀 Come usare

#### Caricare il File Esistente
1. **Apri** `profile-generator-addendum.html` nel browser
2. **Clicca** "📂 Carica profiles_v3_addendum.json"
3. **Seleziona** il file `profiles_v3_addendum.json` dal tuo computer
4. I profili verranno caricati automaticamente

#### Modificare un Profilo
1. **Trova il profilo** da modificare (sono mostrati in card separate)
2. **Modifica i campi**:
   - **Avatar Path**: Percorso relativo dell'immagine (es. `avatars/others/01.png`)
   - **Nome Utente**: Il nome visualizzato (es. "Georgeee")
   - **Descrizione**: Il testo della biografia
   - **Likes**: I timestamp quando il profilo riceverà i "mi piace"

#### Gestire i Likes
- **Aggiungere un Like**: Clicca "+ Aggiungi Like"
- **Rimuovere un Like**: Clicca sul pulsante "✕" accanto al timestamp
- **Modificare un Like**: Cambia il valore direttamente nel campo
- **Auto-compilare**: Clicca "⚡ Auto-compila Likes" per generare timestamp automatici

> 💡 **Nota sui Likes**: I valori sono in millisecondi (es. 45000 = 45 secondi dall'inizio)

#### Caricare Immagini Avatar
1. **Clicca sull'area "📁 Clicca per caricare"** nel profilo desiderato
2. **Seleziona l'immagine** dell'avatar
3. L'immagine verrà mostrata in anteprima
4. Il path dell'avatar viene aggiornato automaticamente

#### Generare il File Aggiornato
1. **Clicca** "✅ Genera profiles_v3_addendum.json"
2. Il file verrà scaricato nel formato JavaScript originale:
   ```javascript
   window.others = {
     "posts" : [...]
   };
   ```
3. Sostituisci il file originale con quello appena generato

### 📋 Formato del File
Il tool genera file nel formato JavaScript compatibile con SMPO:
```javascript
window.others = {
  "posts" : [
    {
      "avatar": "avatars/others/george.png",
      "username": "Georgeee",
      "text": "Descrizione del profilo...",
      "likes": [45000, 50000, 110000, 150000] //4
    }
  ]
};
```

---

## ✂️ 3. Avatar Cutter

### 📋 Cosa fa
Strumento interattivo per ritagliare gli avatar da un'immagine contenente più profili (griglia di avatar).

### 🎯 Funzionalità principali
- ✅ Caricamento immagine sorgente
- ✅ Griglia regolabile (righe e colonne)
- ✅ Ridimensionamento manuale di ogni riquadro
- ✅ Spostamento riquadri con drag & drop
- ✅ Anteprima in tempo reale
- ✅ Export multiplo (tutti gli avatar in una volta)
- ✅ Esportazione coordinate JSON

### 🚀 Come usare

#### Caricare l'Immagine
1. **Apri** `avatar-cutter.html` nel browser
2. L'immagine `avatars-source.jpg` viene caricata automaticamente (se presente nella stessa cartella)
3. Oppure **clicca "Scegli file"** per caricare una tua immagine

#### Configurare la Griglia
1. **Imposta Righe e Colonne** (es. 3 righe × 4 colonne = 12 avatar)
2. **Clicca "Reset Griglia"** per applicare la configurazione
3. Una griglia di riquadri apparirà sull'immagine

#### Regolare i Riquadri
**Selezionare un Riquadro**
- Clicca sul riquadro che vuoi modificare
- Il riquadro selezionato diventa verde

**Ridimensionare**
- Trascina gli **angoli** (8 punti verdi) per ridimensionare
- Trascina i **lati** (punti centrali) per allargare/restringere

**Spostare**
- Trascina il **centro** del riquadro per spostarlo

**Obiettivo**: Fare in modo che ogni riquadro contenga esattamente un avatar senza tagliare il corpo

#### Scaricare gli Avatar
1. **Verifica** che tutti i riquadri siano posizionati correttamente
2. **Clicca** "📥 Scarica Tutti gli Avatar"
3. Verranno scaricati 12 file PNG numerati:
   - `01.png`, `02.png`, `03.png`, ... `12.png`
4. Ogni file contiene un avatar ritagliato

#### Esportare le Coordinate (Opzionale)
1. **Clicca** "📋 Esporta Coordinate"
2. Scarica il file `coordinates.json` con le posizioni di tutti i riquadri
3. Utile per ripetere lo stesso ritaglio in futuro

### 💡 Tips per il Ritaglio
- ✅ Inizia con la griglia base (es. 3×4)
- ✅ Regola prima i riquadri agli angoli
- ✅ Poi sistema quelli centrali
- ✅ Assicurati che ogni avatar sia completo (testa + corpo visibile)
- ✅ Lascia un po' di margine intorno all'avatar

---

## 🔄 Workflow Completo

### Scenario Tipico: Preparare un Esperimento SMPO

#### Step 1: Preparare gli Avatar
1. Usa **Avatar Cutter** per ritagliare le immagini degli avatar
2. Rinomina i file come `01.png`, `02.png`, ecc.
3. Carica le immagini nella cartella `avatars/others/`

#### Step 2: Configurare i Profili
1. Usa **Profile Generator** per creare/modificare i profili
2. Carica le descrizioni per ogni avatar
3. Configura i likes per ogni profilo
4. Genera il file `profiles_v3_addendum.json`

#### Step 3: Gestire i Partecipanti
1. Usa **Participant Manager** per creare la lista partecipanti
2. Assegna le condizioni (1, 2, 3)
3. Inserisci l'URL del questionario
4. Genera i link personalizzati
5. Esporta il CSV finale

#### Step 4: Esecuzione Esperimento
1. Invia a ogni partecipante il suo link personalizzato
2. Il partecipante completa l'esperimento SMPO
3. Viene reindirizzato automaticamente al questionario
4. I dati vengono raccolti

---

## 🔧 Requisiti Tecnici

### Browser Supportati
- ✅ Chrome/Edge (consigliato)
- ✅ Firefox
- ✅ Safari
- ✅ Opera

### Requisiti Minimi
- JavaScript abilitato
- Connessione Internet (per font e librerie CDN)
- Nessuna installazione richiesta!

### File System
Tutti i tool funzionano **standalone**:
- Nessun server richiesto
- Nessun database richiesto
- Tutti i dati restano nel browser

---

## 📚 File di Output

| Tool | Output | Formato | Uso |
|------|--------|---------|-----|
| Participant Manager | `partecipanti_smpo_ita.csv` | CSV | Lista partecipanti con link |
| Profile Generator | `profiles_v3_addendum.json` | JavaScript | Profili avatar per SMPO |
| Avatar Cutter | `01.png`, `02.png`, ... | PNG | Immagini avatar ritagliate |
| Avatar Cutter | `coordinates.json` | JSON | Coordinate ritaglio (opzionale) |

---

## 💡 Tips & Best Practices

### ✅ Cosa Fare
- **Backup frequenti**: Esporta i file regolarmente
- **Testa i link**: Prova almeno un link per condizione prima di inviare
- **Verifica bilanciamento**: Assicurati che le condizioni siano distribuite equamente
- **Usa nomi descrittivi**: Rinomina i file in modo chiaro
- **Documenta le modifiche**: Tieni traccia delle versioni dei file

### ⚠️ Cosa Evitare
- **Non usare virgole** nei nomi dei partecipanti (problemi CSV)
- **Non duplicare ID**: Ogni partecipante deve avere un ID univoco
- **Non modificare i file JSON manualmente**: Usa sempre i tool
- **Non sovrascrivere i file** senza backup

---

## 🆘 Troubleshooting

### Participant Manager

**Problema**: I link non funzionano
- ✅ **Soluzione**: Verifica che l'URL del questionario sia stato codificato con "🔐 Codifica"

**Problema**: Il CSV non si importa
- ✅ **Soluzione**: Verifica che il file segua il formato corretto (vedi esempio)

**Problema**: Gli ID sono duplicati
- ✅ **Soluzione**: Elimina i duplicati e usa assegnazione ID automatica

### Profile Generator

**Problema**: Il file JSON non si carica
- ✅ **Soluzione**: Verifica che sia il file `profiles_v3_addendum.json` corretto
- ✅ L'applicazione supporta sia formato JSON che JavaScript

**Problema**: Le modifiche non vengono salvate
- ✅ **Soluzione**: Devi cliccare "✅ Genera profiles_v3_addendum.json" per salvare

### Avatar Cutter

**Problema**: I riquadri non si muovono
- ✅ **Soluzione**: Prima clicca sul riquadro per selezionarlo (diventa verde)

**Problema**: Gli avatar sono tagliati
- ✅ **Soluzione**: Ridimensiona i riquadri trascinando gli angoli per includere tutto il corpo

---

## 📧 Supporto

Per domande, bug o suggerimenti:
- **Email**: emiliano.pes@uniroma1.it
- **GitHub**: Apri una issue nel repository

---

## 📜 Licenza

Questi tool sono parte del progetto SMPO ITA e sono distribuiti per uso accademico e di ricerca.

---

## 🔄 Changelog

### Versione 1.0 (Ottobre 2025)
- ✅ Rilascio iniziale
- ✅ SMPO Participant Manager completo
- ✅ Profile Generator per addendum
- ✅ Avatar Cutter interattivo

---

**Ultima modifica**: Ottobre 2025  
**Autore**: Strumenti creati per il progetto SMPO ITA  
**Contatto**: emiliano.pes@uniroma1.it
