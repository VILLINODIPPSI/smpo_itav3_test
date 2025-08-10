#LEGGIMI - Assegnazione Condizioni Partecipanti SMPO ITA" 🇮🇹

Nel subfolder ESEMPIO_Risultati_Qualtrics/ sono disponibili due file esempio di risultati esportati da Qualtrics:

Risultati_Qualtrics_esempio.csv
Risultati_Qualtrics_esempio.xlsx

## 📊 Colonne Sistema Qualtrics

| **Colonna** | **Interpretazione** |
|-------------|-------------------|
| StartDate | Data/ora inizio questionario |
| EndDate | Data/ora fine questionario |
| Status | Tipo risposta (Preview, IP Address, etc.) |
| Progress | Percentuale completamento (0-100) |
| Duration (in seconds) | Tempo impiegato per completare |
| Finished | Questionario completato (True/False) |
| ResponseId | ID univoco risposta Qualtrics |
| IPAddress | Indirizzo IP partecipante |

---

## 🎯 Parametri Esperimento SMPO

| **Colonna** | **Interpretazione** |
|-------------|-------------------|
| **p** | ID partecipante (1, 2, 3...) |
| **c** | Condizione: 1=Ostracismo, 2=Inclusione, 3=Sovrainclusione |
| **u** | Nome utente scelto (es. "nomepippo") |
| **d** | Descrizione scritta dal partecipante |
| **av** | ID avatar utilizzato (0, 1, 2...) |

---

## 📝 Scale di Misurazione

### Appartenenza (Nbelong1_1 → Nbelong1_5)
| **Colonna** | **Interpretazione** |
|-------------|-------------------|
| Nbelong1_1 | "Scollegato/a" (negativo) |
| Nbelong1_2 | "Rifiutato/a" (negativo) |
| Nbelong1_3 | "Escluso/a" (negativo) |
| Nbelong1_4 | "Appartengo al gruppo" (positivo) |
| Nbelong1_5 | "Altri interagirebbero con me" (positivo) |

### Autostima (Nsest1_1 → Nsest1_5)
| **Colonna** | **Interpretazione** |
|-------------|-------------------|
| Nsest1_1 | "Bene con me stesso/a" (positivo) |
| Nsest1_2 | "Autostima alta" (positivo) |
| Nsest1_3 | "Apprezzato/a" (positivo) |
| Nsest1_4 | "Insicuro/a" (negativo) |
| Nsest1_5 | "Soddisfatto/a" (positivo) |

### Esistenza Significativa (Nmexist1_1 → Nmexist1_5)
| **Colonna** | **Interpretazione** |
|-------------|-------------------|
| Nmexist1_1 | "Invisibile" (negativo) |
| Nmexist1_2 | "Privo/a di significato" (negativo) |
| Nmexist1_3 | "Inesistente" (negativo) |
| Nmexist1_4 | "Importante" (positivo) |
| Nmexist1_5 | "Utile" (positivo) |

### Controllo (Nctrl1_1 → Nctrl1_5)
| **Colonna** | **Interpretazione** |
|-------------|-------------------|
| Nctrl1_1 | "Potente" (positivo) |
| Nctrl1_2 | "Controllo sull'interazione" (positivo) |
| Nctrl1_3 | "Capacità di influenzare" (positivo) |
| Nctrl1_4 | "Non riesco a influenzare" (negativo) |
| Nctrl1_5 | "Altri decidevano tutto" (negativo) |

### Umore (Mood1_1 → Mood1_8)
| **Colonna** | **Interpretazione** |
|-------------|-------------------|
| Mood1_1 | "Buono" (positivo) |
| Mood1_2 | "Cattivo" (negativo) |
| Mood1_3 | "Amichevole" (positivo) |
| Mood1_4 | "Ostile" (negativo) |
| Mood1_5 | "Arrabbiato" (negativo) |
| Mood1_6 | "Piacevole" (positivo) |
| Mood1_7 | "Felice" (positivo) |
| Mood1_8 | "Triste" (negativo) |

---

## 🔍 Domande di Controllo

| **Colonna** | **Interpretazione** |
|-------------|-------------------|
| Check1 | Riuscito a vedere avatar e descrizioni |
| Check2 | Riuscito a mettere like |
| Q26_1 | "Sono stato/a ignorato/a" |
| Q26_2 | "Sono stato/a escluso/a" |
| Q26_3 | "È piaciuta la mia descrizione" |
| Q28 | Valutazione like ricevuti vs media |

---

*2025 - emiliano.pes@uniroma1.it*
