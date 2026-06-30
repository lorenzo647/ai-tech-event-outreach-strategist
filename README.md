# AI Tech-Event Outreach Strategist

> **Non si ferma a "chi contattare" - quello è ormai commodity. Per ogni figura tech senior genera il messaggio di outreach già scritto e ancorato a un segnale reale e recente della sua azienda. E non inventa mai.**
> Scoring ICP, segmentazione, track giusta e un **message engine** che apre ogni contatto con un complimento concreto sull'ultimo progetto della sua azienda. Pensato per popolare una **grande conferenza tech B2B** con i tech leader giusti e, come extra mile, per acquisire gli sponsor giusti.

![Status](https://img.shields.io/badge/status-POC-yellow) ![Built with](https://img.shields.io/badge/built%20with-Claude-orange) ![Use case](https://img.shields.io/badge/use%20case-B2B%20Tech%20Events-blue) ![License](https://img.shields.io/badge/license-MIT-green)

---

## Executive Summary

**Cosa fa.** Prende un export di contatti (stile Waalaxy / Sales Navigator) e, per ogni figura senior, produce: lo **score ICP**, il **tier** di priorità, la **track** più adatta dell'evento, e soprattutto il **messaggio di outreach pronto da inviare**, che apre con un complimento specifico sull'ultimo progetto reale dell'azienda di quella persona.

**Due fronti.** Il **primario**: portare in sala i tech leader giusti (CTO, VP Eng, Director, Staff/Architect). L'**extra mile**: lo stesso motore identifica le aziende giuste da portare come sponsor e il decisore giusto dentro ognuna, legando l'audience al fatturato dell'evento.

**Perchè il messaggio è il punto.** Targettizzare ("questo è un CTO, contattalo") lo fa già qualsiasi tool. Quello che muove la risposta di una figura senior è un primo messaggio che dimostra che hai letto cosa sta facendo: non "ti invito", ma "ho visto che avete migrato i pagamenti su multi-cloud a downtime zero, e la track Cloud va dritta su questo". Il tool industrializza questa personalizzazione, una per persona.

**La regola che lo rende serio: non inventa.** Il complimento nasce solo da un segnale verificato (`company_recent_signal` / `sponsor_signal`). Se il segnale manca, il sistema non si inventa un progetto: personalizzazione neutra + tag `[SEGNALE DA RICERCARE]`. Un complimento su un progetto falso brucia il contatto: meglio nessun complimento che uno inventato.

**Stato attuale.** POC con dati simulati. Il segnale aziendale, nel POC, vive nel CSV; in produzione lo riempie uno step di enrichment (vedi Roadmap).

---

## 🎯 Profilo del cliente ideale (ICP) - il primo passo, esplicito

Prima di "chi contattare" viene "chi vogliamo in sala". Questo è il profilo, e lo scoring del tool ne è la traduzione in numeri:

- **Audience ideale:** figura tech con potere o influenza decisionale (CTO, CIO, VP/Director of Engineering, Head of Platform/Data/AI, Staff/Principal, Solutions Architect), in scaleup, enterprise o startup tech, preferibilmente già attiva nella community (speaker, organizer, open source, past attendee).
- **Sponsor ideale (extra mile):** azienda che vende ai developer e/o assume in ambito tech, con un segnale recente (lancio, round, hub), e il decisore giusto dentro (DevRel/Marketing o Head of Tech Talent).

L'ICP si applica **due volte**: come filtri di ricerca a monte (Sales Navigator) e come scoring dentro il tool.

---

## 🔌 La pipeline reale (collante: n8n)

Il tool non sostituisce gli strumenti dell'evento: ci sta in mezzo, dove serve il giudizio. Il collante di automazione è **n8n** (open source, self-hostabile); Zapier e Make sono alternative equivalenti.

**Stage 0 - da dove arrivano i dati (la fonte).** Non si parte da una lista a caso. Si parte da una **ricerca su Sales Navigator** con i filtri che sono l'ICP tradotto in ricerca: seniority (CXO, VP, Director), funzione (Engineering, IT), area geografica, dimensione e settore dell'azienda. Quei risultati vengono **estratti in CSV** con Waalaxy o Phantombuster. Il CSV grezzo (titoli disomogenei compresi) entra nel tool, che **normalizza il titolo**, deduce seniority e dominio, e calcola lo scoring. Quindi la fonte e' la ricerca mirata su Sales Navigator; il tool lavora su quell'export.

```
Sales Navigator (ricerca "CTO/VP Eng / aziende dev-first")
        │  estrazione con Waalaxy / Phantombuster
        ▼
   Export CSV / Google Sheets  ──────────►  [ QUESTO TOOL ]
        ▲                                    scoring + track + messaggi ancorati
        │   n8n orchestra i passaggi               │
        │                                          ▼
   Waalaxy (sequenze outreach)  ◄───────  tier + messaggio pronto
        │
        └──►  HubSpot (CRM): tier come property, messaggio come nota, sequenze
```

**Gerarchia, in ordine di serietà:**
- **CSV / Google Sheets** - il formato base. L'output è già un foglio: si apre ovunque, zero attrito, funziona oggi.
- **Waalaxy** - da dove escono i contatti (import da Sales Navigator) e dove rientrano le liste segmentate per l'outreach.
- **HubSpot** - il CRM di destinazione, dove vivono tier, note e sequenze: l'integrazione naturale del prodotto verso un CRM B2B diffuso.
- **n8n** - il collante che, in roadmap, automatizza i passaggi.

**Nota onesta di fattibilita'.** Sales Navigator non ha un'API aperta e Waalaxy non ha API in ingresso (i dati escono solo, via CSV o n8n/Zapier/Make). HubSpot invece ha un'API vera: il push dei tier come property è fattibile, ma in questo POC non e' costruito, sta in roadmap. Niente scraping diretto, niente integrazione dichiarata e non fatta.

---

## 🎯 Lo scenario

Una grande **conferenza tech B2B di due giorni** (nel repo: "DevReach 2026", evento illustrativo e fittizio): community di oltre 250k developer, oltre 1000 tech leader. Contenuti su track tematiche (Cloud & Architectures, AI/ML, DevOps & Platform, Security, ecc.): il tool assegna a ogni contatto la track più affine, da usare come gancio nel messaggio. Per gli sponsor il valore e' incontrare quei developer: assumere, mostrare prodotti dev-first, fare networking B2B. I dati sono simulati e l'evento è fittizio; il tool si adatta a qualsiasi conferenza tech B2B reale.

---

## 🚀 Quickstart (3 minuti)

1. Apri [https://claude.ai](https://claude.ai), nuova conversazione.
2. Incolla [`docs/system-prompt.md`](docs/system-prompt.md) come primo messaggio.
3. Incolla [`data/leaders.csv`](data/leaders.csv) (e, per l'extra mile, [`data/sponsors.csv`](data/sponsors.csv)).
4. In ~20 secondi: scoring, track, e i messaggi pronti. Esempio completo in [`examples/sample-output.md`](examples/sample-output.md).

---

## 📂 Struttura

```
ai-tech-event-outreach-strategist/
├── docs/
│   ├── system-prompt.md         # Due fronti (leader + sponsor), scoring, track, Message Engine + grounding
│   ├── benchmark-events.md      # Benchmark audience, funnel, no-show
│   └── icp-glossary.md          # Definizioni (ICP, sponsor fit, segnale, grounding, pipeline)
├── data/
│   ├── leaders.csv              # 12 tech leader (focus) con company_recent_signal
│   └── sponsors.csv             # 6 aziende target sponsor (extra mile) con sponsor_signal
├── examples/
│   ├── examples_README.md
│   └── sample-output.md         # Output completo: leader + sponsor, messaggi pronti, fallback anti-invenzione
├── README.md
└── LICENSE
```

---

## 🧠 Scelte di design

**Perchè il messaggio e non il targeting.** Il targeting lo fa già l'AI. Il collo di bottiglia umano è scrivere decine di primi messaggi personalizzati e veri. Lì il tool fa la differenza.

**Perchè la regola di grounding è sacra.** Un LLM libero "indovina" l'ultimo progetto. Un complimento plausibile ma falso è peggio del silenzio. Quindi: complimento solo da segnale verificato, altrimenti flag esplicito.

**Perchè l'extra mile sponsor.** Riempire la sala e riempire gli stand sono lo stesso problema visto da due lati: una persona/azienda, un segnale recente, un complimento vero, un invito. Aggiungerlo lega il lavoro di audience al fatturato dell'evento.

**Perchè n8n come collante.** Open source, self-hostabile, leggibile anche senza essere sviluppatori. Zapier/Make fanno lo stesso, ma n8n è la scelta più trasparente per chi vuole capire e controllare i flussi.

---

## 🗺️ Roadmap

- **v1.1 - Enrichment del segnale.** Uno step (n8n + ricerca web) che per ogni azienda trova l'ultimo progetto reale e riempie `company_recent_signal` con fonte e data, mantenendo il grounding.
- **v1.2 - Push in HubSpot.** Scrivere tier e messaggio come property/nota sul contatto via API HubSpot, e far partire la sequenza.
- **v1.3 - Sponsor scoring arricchito.** Integrare segnali di funding/hiring per qualificare meglio le aziende.
- **v1.4 - No-show predittivo.** Da regole a soglia a modello sui dati storici dell'evento.

---

## ⚠️ Limitazioni note

- **POC con dati simulati**: contatti, aziende e segnali sono realistici ma fittizi, così come l'evento.
- **Il segnale, nel POC, è fornito**: l'enrichment automatico è roadmap, non è costruito.
- **Le integrazioni (HubSpot, n8n) sono descritte come direzione, non implementate.**
- **Qualità = qualità del CSV**: un export sporco produce uno scoring sporco.

---

## 👤 Built by

**Lorenzo Ricci** - Project Manager & Communications Specialist

Nasce da un metodo che uso quando scrivo a qualcuno che conta: non un messaggio generico, ma qualcosa di vero e recente che la sua azienda ha fatto. L'ho messo dentro un sistema, con una regola ferma: mai inventare il complimento. Il resto - scoring, track, drop-off, fronte sponsor — serve a far arrivare quel messaggio alla persona giusta, prima che si perda per strada.

## 📄 License

MIT
