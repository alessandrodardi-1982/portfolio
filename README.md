# Portfolio — Alessandro Dardi

**Operations & Digital Transformation** · Bologna

🔗 **Portfolio online:** https://alessandrodardi-1982.github.io/portfolio/

---

## Di cosa si tratta

Questo non è un sito che elenca competenze. È una raccolta di problemi operativi reali — vissuti in 8 anni di service management industriale — trasformati in strumenti digitali funzionanti.

Ogni progetto nasce da una domanda concreta nata sul campo: *come faccio a sapere chi ho disponibile vicino a quel cliente? Come riduco il tempo per fare un preventivo? Come trasformo dati grezzi in una decisione?* La risposta non è una riga sul CV, è uno strumento che si può apr ire, usare, testare.

**Principio guida:** non dichiaro competenze, le dimostro.

---

## Struttura del portfolio

| # | Sezione | Contenuto |
|---|---|---|
| 00 | **Chi sono** | Posizionamento: dalle operations industriali agli strumenti digitali |
| 01 | **Lavori** | 8 progetti end-to-end (automazione, AI, analisi, gestione) |
| 02 | **Analisi Dati** | 4 dashboard generate con Claude API |
| 03 | **Applicativi** | CRM per PMI |
| 04 | **Agente AI** | Agente di triage per supporto tecnico industriale |
| 05 | **AI Assessment** | Documento strategico di adozione AI per una PMI |
| 06 | **Strumenti** | Stack tecnico usato nei progetti |
| 07 | **Formazione** | Master e percorsi formativi, con attestati verificabili |

---

## Progetti — sezione Lavori

| Codice | Progetto | Problema reale | Stack |
|---|---|---|---|
| A1 | Automazione report settimanale | Generare un report CRM ogni venerdì senza intervento manuale | n8n, Claude API, Google Sheets |
| A2 | Performance Fornitori H1 2026 | Confrontare fornitori su prezzo, qualità e tempi di consegna | Tableau Public |
| A6 | Mappa operativa interventi | Sapere quale tecnico è disponibile vicino al cliente | Leaflet.js, OpenStreetMap |
| A7 | Analisi consumi energetici | Individuare sprechi e anomalie nei consumi di reparto | Chart.js, Claude API |
| A8 | Gestione ricambi & magazzino | Evitare rotture di stock sui ricambi critici, ABC analysis | Chart.js, Claude API |
| A9 | Preventivatore AI | Tradurre una richiesta cliente in linguaggio naturale in un preventivo strutturato | Claude API, Netlify Functions |
| A10 | Audit impianti | Guidare un'ispezione tecnica e generare il verbale automaticamente | Claude API, Netlify Functions |

**CRM per PMI** (sezione Applicativi): gestione anagrafica clienti, storico interventi e pipeline — single-file HTML, zero dipendenze server.

**Agente AI di triage** (sezione Agente AI): smista le richieste di assistenza tecnica per urgenza, tipo guasto e tecnico suggerito. L'AI accelera, l'umano decide.

**AI Readiness Assessment** (sezione AI Assessment): documento strategico — score di maturità AI, mappa use case, roadmap a 18 mesi con ROI, governance e nota EU AI Act. Non è un tool, è la visione che li ordina.

> Tutti i progetti usano dataset sintetici e aziende fittizie (Termoflex Srl, TecnoService Industriale Srl, Meridian Industries Srl), costruiti su pattern reali del settore industriale. Nessun dato reale di clienti o aziende è stato usato.

---

## Formazione

- **Master in Digital Restart** — Talent Garden (Feb–Mag 2026): digital tools, project management agile/tradizionale, AI tools applicati, marketing digitale. [Attestato verificabile](https://certificates.talentgarden.com/8271f5c6-8bea-4f43-8568-26cb49eadb82#acc.Sqc5GMEv).
- Corso pratico **n8n e JavaScript per automazioni e agenti AI** — Udemy (Mag 2026)
- Corso **Intelligenza artificiale e le sue applicazioni pratiche** — Demetra Formazione (Mag 2025)
- **Laurea in Ingegneria Gestionale** — Alma Mater Studiorum, Università di Bologna

CV completo scaricabile dalla sezione Contatti del portfolio.

---

## Stack tecnico

`n8n` · `Claude API` · `Tableau Public` · `Excel avanzato` · `Python (base)` · `JavaScript (base)` · `Leaflet.js` · `Chart.js` · `D3.js` · `Docker (base)` · `GitHub Pages` · `Netlify Functions` · `CRM`

I badge "base" o "nuovo per me" nel sito indicano onestamente il livello reale di padronanza di uno strumento — coerente con l'approccio del portfolio: niente è gonfiato.

---

## Architettura

- **Hosting principale:** GitHub Pages (statico, gratuito)
- **Hosting con AI:** Netlify, solo per i progetti che richiedono una funzione serverless come proxy verso Claude API (mai chiave API esposta nel browser)
- **Generazione contenuti AI:** Claude API (`claude-sonnet-4-6`) via chiamata diretta o tramite proxy Netlify (`netlify/functions/claude-proxy.js`)
- **Metodo di lavoro:** ogni modifica passa prima da una repo/ambiente di test prima di arrivare in produzione

---

## Contatti

Profilo LinkedIn e contatti diretti disponibili nella sezione Contatti del sito.

---

> *Non ho imparato strumenti per aggiungerli al CV. Ho risolto problemi reali, e gli strumenti sono venuti di conseguenza.*
