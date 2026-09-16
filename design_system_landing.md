# Design System — Alessandro Dardi Landing Page
**Stile ispirato a antonioguadagno.it — adattato al profilo Operations & AI**
Creato: settembre 2026

---

## Principio guida

Layout light (sfondo bianco), professionale, senza effetti dark né gradienti pesanti. Nessun elemento da "fuffa guru": zero promesse vaghe, zero decorazioni inutili. Il contenuto parla da solo, il design lo supporta senza sovrastarlo.

---

## Font

```html
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400&family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
```

| Ruolo | Font | Pesi usati |
|---|---|---|
| Titoli (h1, h2, h3) | Playfair Display, serif | 400, 600, 700 |
| Corpo, UI, bottoni | Inter, sans-serif | 400, 500, 600, 700 |

**Regola:** Playfair Display solo per titoli di sezione e headline. Inter per tutto il resto: paragrafi, label, bottoni, navbar, footer.

---

## Palette colori

```css
/* Colori principali */
--navy:       #1a1a2e;   /* testo principale, bottoni dark, footer bg */
--navy-mid:   #2d2d4e;   /* hover bottoni dark */
--white:      #ffffff;   /* sfondo sezioni primarie */
--gray-bg:    #f7f7fb;   /* sfondo sezioni alternate (logo band, stats, modal input) */
--border:     #e0e0ea;   /* bordi card, input, separatori */
--border-light: #e8e8ee; /* bordi nav, sezioni, tabelle */
--border-dark: #d0d0e0;  /* bordi bottoni outline */

/* Testo */
--text-main:  #1a1a2e;   /* testo principale */
--text-mid:   #555555;   /* testo secondario (paragrafi, descrizioni) */
--text-soft:  #888888;   /* label, date, testo terziario */
--text-muted: #aaaaaa;   /* label uppercase piccole */

/* Accenti semantici (solo dove portano significato) */
--green:      #16a34a;   /* stato CHIUSO / positivo */
--amber:      #d97706;   /* stato APERTO / warning */
--blue:       #2563eb;   /* stato IN LAVORAZIONE */
--red:        #dc2626;   /* urgenza alta */

/* Footer */
--footer-bg:  #1a1a2e;
--footer-text: rgba(255,255,255,0.75);
--footer-label: rgba(255,255,255,0.4);
--footer-border: rgba(255,255,255,0.1);
--footer-muted: rgba(255,255,255,0.35);
```

---

## Struttura pagina (scroll unico)

```
NAV fissa (68px)
│
├── HERO          — sfondo #fff — 2 colonne: testo sx + foto circolare dx
├── LOGO BAND     — sfondo #f7f7fb — pill con tecnologie / partner
├── CHI SONO      — sfondo #fff — 2 colonne: foto sx + testo dx
├── STATS         — sfondo #f7f7fb — 3 colonne con numero grande + label
├── PROGETTI      — sfondo #fff — griglia 2x2 di card
└── FOOTER        — sfondo #1a1a2e — 3 colonne + bottom bar
```

**Regola alternanza:** sezioni bianche e grigio-chiaro si alternano sempre. Mai due sezioni dello stesso colore di fila.

---

## Componenti

### Navbar

```css
position: fixed; top: 0; z-index: 100;
background: rgba(255,255,255,0.96);
backdrop-filter: blur(8px);
border-bottom: 1px solid #e8e8ee;
height: 68px;
```

- Brand: Playfair Display 600, 1.15rem, colore `#1a1a2e`
- Link: Inter 500, 0.875rem, colore `#555` → hover `#1a1a2e`
- Max-width contenuto: 1100px, padding 0 32px
- Hamburger mobile: visibile sotto 768px

---

### Hero

```css
padding: 128px 0 80px;   /* top padding alto per compensare nav fissa */
display: grid;
grid-template-columns: 1fr auto;
align-items: center;
gap: 64px;
```

- **h1:** Playfair Display 700, `clamp(2rem, 4vw, 2.9rem)`, line-height 1.18, letter-spacing -0.03em
- **p:** Inter 400, 1.1rem, colore `#555`, max-width 680px, line-height 1.7
- **Foto:** 260px × 260px, border-radius 50%, border 4px solid `#f0f0f5`, object-position center center
- La foto deve essere già ritagliata in cerchio o avere soggetto centrato — il CSS applica solo `border-radius: 50%`, nessun crop aggiuntivo
- Mobile (≤768px): colonna singola, foto sopra (160×160px), testo centrato

---

### Bottoni

```css
/* Primario — dark */
.btn-dark {
  background: #1a1a2e; color: #fff;
  padding: 14px 28px; border-radius: 6px;
  border: 2px solid #1a1a2e;
  font-family: Inter; font-weight: 600; font-size: 0.95rem;
}
.btn-dark:hover { background: #2d2d4e; }

/* Secondario — outline */
.btn-outline {
  background: transparent; color: #1a1a2e;
  padding: 14px 28px; border-radius: 6px;
  border: 2px solid #d0d0e0;
}
.btn-outline:hover { border-color: #1a1a2e; }
```

**Regola:** mai usare colori vivaci per i bottoni principali. Dark o outline, nient'altro.

---

### Section label (eyebrow)

```css
.section-label {
  font-size: 0.75rem; font-weight: 600;
  color: #888; letter-spacing: 0.12em;
  text-transform: uppercase;
  margin-bottom: 16px; display: block;
}
```

Usato sopra ogni h2 di sezione per contestualizzare. Testo breve (1-2 parole).

---

### Titoli di sezione (h2)

```css
font-family: 'Playfair Display', serif;
font-weight: 700;
font-size: clamp(1.7rem, 3.5vw, 2.4rem);
line-height: 1.25;
letter-spacing: -0.02em;
color: #1a1a2e;
margin-bottom: 24px;
```

---

### Sezione Chi sono

```css
.about {
  padding: 88px 0; background: #fff;
}
.about-inner {
  max-width: 760px; margin: 0 auto; padding: 0 32px;
}
```

- **Foto rimossa** da questa sezione — appare solo nel hero
- Layout: colonna singola centrata, max-width 760px
- Titolo h2 e section-label: `text-align: center`
- Paragrafi: `text-align: justify`, `hyphens: auto`

---

### Pill (logo band / tag stack)

```css
.pill {
  background: #fff; border: 1px solid #e0e0ea;
  border-radius: 24px; padding: 8px 20px;
  font-size: 0.875rem; font-weight: 500; color: #555;
}
```

Usato per elencare tecnologie, strumenti, competenze. Layout `flex-wrap: wrap; justify-content: center; gap: 12px`.

---

### Stat (numeri grandi)

```css
.stat-num {
  font-family: 'Playfair Display', serif;
  font-size: 2.8rem; font-weight: 700;
  color: #1a1a2e; line-height: 1;
}
.stat-label {
  font-size: 0.8rem; font-weight: 600;
  color: #999; letter-spacing: 0.1em;
  text-transform: uppercase;
}
```

Griglia 3 colonne, testo centrato. Mobile: colonna singola.

---

### Card progetto

```css
.project-card {
  background: #fff;
  border: 1.5px solid #e0e0ea;
  border-radius: 10px;
  padding: 28px 24px;
  transition: border-color 0.2s, box-shadow 0.2s;
}
.project-card:hover {
  border-color: #1a1a2e;
  box-shadow: 0 4px 20px rgba(26,26,46,0.08);
}
```

Struttura interna:
- Icona emoji (1.5rem, margin-bottom 14px)
- Nome (Inter 700, 1.05rem, `#1a1a2e`)
- Descrizione (Inter 400, 0.9rem, `#666`, line-height 1.65)
- Label costo (Inter 600, 0.75rem, `#aaa`, uppercase)
- Bottoni azione (demo + link esterno)

Griglia 2 colonne desktop, 1 colonna mobile (≤640px).

---

### Modal

```css
.modal {
  background: #fff;
  border-radius: 12px;
  max-width: 520px;
  padding: 36px;
  box-shadow: 0 20px 60px rgba(0,0,0,0.15);
}
.modal-overlay {
  background: rgba(26,26,46,0.5);
  backdrop-filter: blur(4px);
}
```

- Input/textarea/select: sfondo `#f7f7fb`, bordo `#e0e0ea`, focus bordo `#1a1a2e`
- Bottone azione: stesso stile `.btn-dark`
- Output demo: sfondo `#f7f7fb`, bordo `#e0e0ea`
- Mobile (≤560px): drawer dal basso, border-radius 12px 12px 0 0

---

### Footer

```css
background: #1a1a2e;
padding: 64px 0 40px;
display: grid;
grid-template-columns: 1fr 1fr 1fr;
gap: 48px;
```

- Intestazioni colonne: Inter 600, 0.8rem, uppercase, `rgba(255,255,255,0.4)`
- Link e testo: `rgba(255,255,255,0.75)` → hover `#fff`
- Bottom bar: border-top `rgba(255,255,255,0.1)`, testo `rgba(255,255,255,0.35)`, 0.8rem

---

## Layout generale

```css
max-width: 1100px;
margin: 0 auto;
padding: 0 32px;
```

Applicato a tutti i contenitori interni con classe `.xxx-inner`.

---

## Responsive breakpoint principale

```css
@media (max-width: 768px) {
  /* nav: hamburger menu */
  /* hero: colonna singola, foto sopra */
  /* about: colonna singola */
  /* footer: colonna singola */
}

@media (max-width: 640px) {
  /* project-grid: 1 colonna */
}

@media (max-width: 520px) {
  /* stats: 1 colonna */
}

@media (max-width: 560px) {
  /* modal: drawer dal basso */
}
```

---

## Regole di stile da rispettare sempre

1. **Mai dark mode** — sfondo sempre bianco o `#f7f7fb`. Il dark è riservato solo al footer e ai bottoni primari.
2. **Mai colori vivaci come accent principale** — niente blu elettrico, verde acido, arancio. I colori semantici (verde/amber/rosso) si usano solo per stati (APERTO, CHIUSO, urgenza).
3. **Playfair Display solo per titoli** — mai per UI, label, bottoni.
4. **Nessuna animazione automatica** — solo transizioni su hover/focus (0.2s). Niente scroll animations, parallax, fade-in automatici.
5. **Tono del copy: concreto, senza promesse vaghe** — mai headline da "fuffa guru". Il contenuto dimostra, non vende.
6. **Border-radius contenuto:** 6px per bottoni, 10px per card, 12px per modal, 24px per pill. Mai tutto tondo su card o sezioni.
7. **Sezioni alternate:** bianco (`#fff`) e grigio chiaro (`#f7f7fb`) si alternano sempre.
8. **Max-width 1100px** centrato — mai full-width su schermi grandi.

---

## Checklist prima di pubblicare

- [ ] Font Google Fonts caricati con `preconnect`
- [ ] Nav fissa con hamburger funzionante su mobile
- [ ] Foto profilo: 520×520px minimo, già ritagliata in cerchio o soggetto centrato, sfondo neutro. Il CSS applica `border-radius: 50%` — non serve crop aggiuntivo. `object-position: center center`
- [ ] Sezioni in ordine: Hero → Band → Chi sono → Stats → Progetti → Footer
- [ ] Alternanza colori sezioni rispettata
- [ ] Modal funzionanti: open/close su overlay click + bottone ✕
- [ ] Footer con 3 colonne (chi sei, contatti, link)
- [ ] Responsive testato su 375px (iPhone), 768px (tablet), 1280px (desktop)
