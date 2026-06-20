[README (1).md](https://github.com/user-attachments/files/29162960/README.1.md)
[README.md](https://github.com/user-attachments/files/29162312/README.md)
[readme_aggiornato.md](https://github.com/user-attachments/files/29089521/readme_aggiornato.md)
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
| A7 | **Strategia AI** | AI Readiness Assessment per PMI industriale: maturità, use case map, roadmap 18 mesi, governance |
| A8 | **Analisi energetica / AI** | Dashboard con diagnosi AI su consumi energetici: trend per reparto, anomalie rilevate, azioni correttive |
| A9 | **Gestione magazzino / AI** | Dashboard ricambi con ABC analysis, alert stock critico e suggerimenti riordino AI |
| A10 | **Preventivatore AI** | Da una richiesta in linguaggio naturale a una bozza preventivo strutturata con voci, prezzi e IVA |

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
- Lista laterale scrollabile sincronizzata con la mappa
- KPI in header: attività aperte, da pianificare, pianificate, totale

🔗 **Dashboard:** https://tencoservice-mappa.netlify.app/mappa_operativa.html

**File:**
- `mappa_operativa.html` — applicativo completo single-file (repo separata: `tecnoservice-mappa`)

---

## A7 — AI Readiness Assessment — Meridian Industries Srl

Documento strategico completo per guidare l'adozione dell'AI in una PMI industriale italiana. Nasce dall'esperienza diretta come Service Manager: i dati c'erano, gli strumenti c'erano — mancava un metodo per capire da dove partire e cosa era realistico aspettarsi.

Il caso Meridian Industries è fittizio ma costruito su pattern reali di PMI manifatturiere italiane. La struttura è replicabile su qualsiasi cliente industriale.

**Contenuto del documento:**
- **Sezione 00** — Origine del progetto: perché questo documento esiste
- **Sezione 01** — Company Snapshot: chi è Meridian, strumenti attuali, problemi dichiarati
- **Sezione 02** — AI Readiness Assessment: score su 4 assi (Dati, Processi, Persone, Infrastruttura) con radar chart e tabella progressione
- **Sezione 03** — Use Case Map: 6 use case valutati per impatto e difficoltà con bubble chart interattivo
- **Sezione 04** — Roadmap 18 mesi: 3 fasi con milestone, attività e ROI stimato per ciascuna
- **Sezione 05** — AI Governance Framework: rischi, principi operativi, KPI di controllo, nota EU AI Act

**Score complessivo:** 9/20 — AI Ready: Fase Iniziale

**Collegamento con il portfolio:**
- UC1 (triage assistenza) → prototipo funzionante in A4
- UC2 (manutenzione predittiva) → prototipo funzionante in A5

**Stack:** HTML/CSS/JS · Chart.js · Sora + DM Sans + JetBrains Mono

🔗 **Live:** https://alessandro-dardi.netlify.app/meridian_ai_assessment.html

**File:**
- `meridian_ai_assessment.html` — documento completo single-file

---

## A8 — Analisi consumi energetici

Dashboard interattiva con AI integrata per il monitoraggio e la diagnosi dei consumi energetici di un impianto industriale (scenario fittizio: Termoflex Srl). I dati ci sono in quasi tutte le aziende — il problema è che nessuno li legge in modo sistematico.

**Stack:** HTML/CSS/JS · Chart.js · Claude API · Netlify Functions

**Funzionalità:**
- Trend mensili per 4 reparti (Produzione, Refrigerazione, Compressori, Servizi generali)
- 3 anomalie rilevate con scostamento percentuale e descrizione operativa
- Bottone "Analizza con AI": Claude riceve i dati e restituisce una diagnosi con azioni correttive concrete
- KPI header: consumo totale (942.504 kWh), costo stimato, anomalie, risparmio potenziale

🔗 **Dashboard:** https://cheery-froyo-86386e.netlify.app/dashboard_energia.html

**File:**
- `dashboard_energia.html` — dashboard completa single-file (repo: `energia-consumi`)

---

## A9 — Gestione ricambi e magazzino

Dashboard interattiva con AI integrata per il monitoraggio del magazzino ricambi (scenario fittizio: Termoflex Srl). Il ricambio giusto deve esserci al momento del guasto — rotture di stock significano downtime, magazzino sovraccarico significa capitale immobilizzato.

**Stack:** HTML/CSS/JS · Chart.js · Claude API · Netlify Functions

**Funzionalità:**
- ABC analysis su 20 articoli (18 mesi di storico utilizzi)
- Alert automatici: 1 articolo esaurito, 3 sotto scorta, 4 fermi da troppo tempo
- Suggerimenti riordino con quantità, costo stimato e lead time
- Bottone "Analizza con AI": Claude sintetizza le criticità e le priorità operative
- KPI header: articoli totali, esauriti, sotto scorta, valore magazzino, valore fermo

🔗 **Dashboard:** https://benevolent-malasada-6e21e2.netlify.app/dashboard_magazzino.html

**File:**
- `dashboard_magazzino.html` — dashboard completa single-file (repo: `magazzino-ricambi`)

---

## A10 — Preventivatore AI

Applicativo web con AI integrata per la generazione assistita di preventivi tecnici (scenario fittizio: Termoflex Srl). Costruire un preventivo è un processo lento e inconsistente — l'AI lo accelera partendo da una descrizione in linguaggio naturale.

**Stack:** HTML/CSS/JS · Claude API · Netlify Functions

**Funzionalità:**
- Form con descrizione libera della richiesta cliente, tipo impianto e livello urgenza
- 4 esempi rapidi cliccabili (compressore, frigo, manutenzione programmata, pompa)
- Listino Termoflex completo nel prompt (manodopera, maggiorazioni, ricambi principali)
- Output strutturato: tabella voci, quantità, prezzi, IVA, note operative, numero preventivo
- Bottone stampa / salva PDF

🔗 **Applicativo:** https://magenta-daffodil-07f9ec.netlify.app/preventivatore_ai.html

**File:**
- `preventivatore_ai.html` — applicativo completo single-file (repo: `preventivatore-ai`)

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

`HTML/CSS/JS` · `Python` · `pandas` · `scikit-learn` · `Leaflet.js` · `n8n` · `Claude API` · `Chart.js` · `Tableau` · `GitHub` · `Netlify` · `Docker` · `AI Strategy`

---

## Repos

| Repo | Ruolo |
|---|---|
| `alessandrodardi-1982/portfolio` | Portfolio principale — deploy su `alessandro-dardi.netlify.app` |
| `alessandrodardi-1982/tecnoservice-mappa` | Mappa operativa — deploy su `tencoservice-mappa.netlify.app` |
| `alessandrodardi-1982/tecnoservice-chat` | Agente AI triage — deploy su `tecnoservice-chat.netlify.app` |

---

## Nota sui dati

Tutti i dataset e i casi aziendali sono fittizi ma realistici, costruiti su pattern tipici della manutenzione industriale italiana. I progetti illustrano l'approccio metodologico, non previsioni operative su dati reali.

> L'AI accelera — l'umano decide.
