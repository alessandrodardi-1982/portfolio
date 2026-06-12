[README (2).md](https://github.com/user-attachments/files/28883221/README.2.md)
# Portfolio — Operations, Automazione, AI applicata

Portfolio professionale di **Alessandro Dardi** — riposizionamento da Service Manager industriale verso ruoli ibridi Operations + Digital.

🔗 **Sito live:** https://alessandro-dardi.netlify.app

Il principio è semplice: il portfolio non dichiara competenze, le dimostra. Ogni lavoro nasce da un problema operativo reale e arriva a uno strumento funzionante.

---

## I lavori

| # | Strumento | Cosa risolve |
|---|-----------|--------------|
| A1 | **n8n** | Report settimanale automatico: legge i dati, genera una dashboard con Claude API, la invia via email |
| A2 | **Tableau** | Analisi performance fornitori su 7 fornitori e 6 mesi |
| A3 | **Excel avanzato** | Dashboard costi manutenzione con formule avanzate e KPI |
| A4 | **AI applicata** | Chat conversazionale che trasforma una richiesta libera in un ticket strutturato |
| A5 | **Python / Machine Learning** | Manutenzione predittiva: stima la probabilità di guasto e suggerisce il tecnico |
| A6 | **Leaflet.js / Gestione operativa** | Mappa operativa interventi tecnici sul territorio — evoluzione digitale di un DB Excel reale |

---

## A5 — Manutenzione predittiva (Machine Learning)

Modello che analizza lo storico interventi e stima, per ogni macchinario, la probabilità di guasto imminente. Suggerisce inoltre il tecnico in base alla specializzazione.

**Stack:** Python · pandas · scikit-learn (Random Forest)

**Risultati:**
- 75% di accuratezza sul test set per la previsione di guasto imminente
- Le variabili che pesano di più sono età macchinario (27%) e ore di utilizzo (27%) — coerenti con la logica della manutenzione reale
- Output: parco macchine ordinato per rischio, con motivazione in chiaro e tecnico consigliato, esportabile in CSV

🔗 **Dashboard:** https://alessandro-dardi.netlify.app/dashboard_manutenzione_predittiva.html

### Eseguire lo script

```bash
pip install pandas numpy scikit-learn joblib
python manutenzione_predittiva.py
```

Lo script genera il dataset, addestra il modello, ne stampa la valutazione (accuratezza + feature importance) ed esporta i file. Risultati riproducibili a ogni esecuzione (seed fissi).

**File:**
- `manutenzione_predittiva.py` — script completo e commentato
- `crm_ml_dataset.csv` — dataset di esempio (500 interventi)
- `dashboard_manutenzione_predittiva.html` — visualizzazione dei risultati

---

## A6 — Mappa operativa interventi

Dashboard operativa web con mappa geografica interattiva per la gestione degli interventi tecnici sul territorio. Nasce da un problema reale: coordinare tecnici su un'area ampia con centinaia di attività aperte (chiamate urgenti, manutenzioni programmate, interventi) senza avere una visione geografica immediata.

La soluzione originale era un DB Excel con una colonna "Zona" — un numero che identificava l'area geografica del cliente, assegnato tramite VLOOKUP su una tabella lookup città→zona. Questo strumento ne è l'evoluzione digitale.

**Stack:** Leaflet.js · OpenStreetMap · HTML/CSS/JS · Excel → JSON

**Funzionalità:**
- Mappa interattiva con marker colorati per stato (Da fare, Pianificata, Stand by, Da ripianificare, Chiusa)
- Filtri a selezione multipla per Stato, Tipo attività e Tecnico
- Priorità assegnabile dal coordinatore direttamente dal popup (Alta / Media / Bassa) con persistenza in localStorage
- Bordo colorato sui marker in base alla priorità assegnata
- Lista laterale scrollabile sincronizzata con la mappa
- KPI in header: attività aperte, da pianificare, pianificate, totale

🔗 **Dashboard:** https://tencoservice-mappa.netlify.app/mappa_operativa.html

**File:**
- `mappa_operativa.html` — applicativo completo single-file (repo separata: `tecnoservice-mappa`)

---

## Agente AI — Triage supporto tecnico

Agente per la gestione delle richieste di supporto tecnico industriale (scenario fittizio: TecnoService Industriale Srl). Flusso a 6 step con revisione umana prima dell'assegnazione al tecnico.

🔗 **Live:** https://tecnoservice-chat.netlify.app/chat_assistenza.html

**Concetto chiave:** L'AI suggerisce — l'umano decide.

---

## CRM per PMI

CRM single-file HTML per aziende industriali medio-piccole. Mobile-responsive, zero dipendenze server. Anagrafica clienti, storico interventi, stati pipeline, filtri, export.

🔗 **Live:** https://alessandro-dardi.netlify.app/crm_pmi.html

---

## Stack del progetto

`HTML/CSS/JS` · `Python` · `pandas` · `scikit-learn` · `Leaflet.js` · `n8n` · `Claude API` · `Tableau` · `GitHub` · `Netlify` · `Docker`

---

## Repos

| Repo | Ruolo |
|---|---|
| `alessandrodardi-1982/portfolio` | Portfolio principale — deploy su `alessandro-dardi.netlify.app` |
| `alessandrodardi-1982/tecnoservice-mappa` | Mappa operativa — deploy su `tencoservice-mappa.netlify.app` |
| `alessandrodardi-1982/tecnoservice-chat` | Agente AI triage — deploy su `tecnoservice-chat.netlify.app` |

---

## Nota sui dati

Tutti i dataset sono fittizi ma realistici, costruiti su casi tipici della manutenzione industriale. I progetti illustrano l'approccio metodologico, non previsioni operative su dati reali.

> L'AI accelera — l'umano decide.
