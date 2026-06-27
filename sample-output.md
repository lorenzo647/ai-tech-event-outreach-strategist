# Output di esempio - AI Tech-Event Outreach Strategist

> Generato dal system prompt (`docs/system-prompt.md`) su `data/leaders.csv` (12 tech leader) e `data/sponsors.csv` (6 aziende). Numeri verificabili nel blocco `<calcoli_interni>`. Il cuore sono i messaggi pronti, ognuno ancorato al segnale reale dell'azienda. Dove il segnale manca, il sistema NON inventa.

---

```
<calcoli_interni>
LEADER  score -> Tier | Track | Drop-off | Segnale
L001 Marta Vinci      100 A | Cloud & Architectures     | BASSO | SI
L002 Davide Aru        91 A | Languages & Architectures | BASSO | SI
L014 Ilaria Conti      90 A | Cloud & Architectures     | BASSO | SI
L010 Tomas Varga       86 A | Languages & Architectures | ALTO  | SI
L012 Federico Neri     86 A | AI/ML                     | -     | SI
L009 Sara Moretti      79 A | Security                  | BASSO | SI
L017 Andrea Lombardi   77 A | Security                  | -     | SI
L015 Jonas Berg        66 B | Data Engineering          | BASSO | SI
L003 Elena Fabbri      62 B | Data Engineering          | ALTO  | SI
L007 Anna Castelli     60 B | Cloud & Architectures     | BASSO | SI
L004 Samuel Okoro      56 B | AI/ML                     | -     | MANCA
L006 Luca Bertoni      36 C | Frontend                  | -     | MANCA
LEADER TIER: A=7 | B=4 | C=1   Segnale mancante: L004, L006

SPONSOR  score -> Tier | Decisore | Segnale
S001 Vectorly    92 A | Head of Developer Relations | SI
S002 Forgepipe   88 A | Co-founder & CEO            | SI
S004 Cloudbridge 71 A | Solutions Architect         | SI
S003 Banca Aurea 65 B | Head of Tech Talent         | SI
S005 Stamp       63 B | Marketing Lead              | SI
S006 Reti Spa    20 Out| Brand Manager              | MANCA
SPONSOR TIER: A=3 | B=2 | Out=1
</calcoli_interni>
```

---

### 1. EXECUTIVE SUMMARY
12 tech leader: 7 Tier A (tutti decisori core, ottimi per il palco), 4 Tier B, 1 Tier C. Track piu' affollate: Cloud e AI/ML. Due registrati di valore a rischio drop-off ALTO (L010 Tier A, L003 Tier B). Due segnali aziendali mancanti (L004, L006) marcati da ricercare. Sul fronte sponsor: 3 aziende Tier A ad alta priorita' commerciale (vendono ai dev e/o assumono, con segnale recente), 2 Tier B, 1 da scartare.

### 2. TECH LEADER — SCORING, TRACK & DROP-OFF
Tier A 🟢 (7), Tier B 🟢 (4), Tier C 🟡 (1). Vedi tabella. Concentrazione di decisori su Cloud/Security/Backend: per i keynote ai Tier A conviene mettere davanti quelle track.

### 3. MESSAGGI PRONTI — LEADER

**[Tier A · 1:1 LinkedIn · track Cloud & Architectures] L001 Marta Vinci (CTO, Nuvola Pay)**
> Ciao Marta, ho letto della migrazione della vostra piattaforma pagamenti su multi-cloud a downtime zero: su un sistema di pagamenti e' la parte che fa piu' paura, e dirla a downtime zero non e' banale. A DevReach 2026 la track Cloud & Architectures va dritta su questi temi: mi piacerebbe averti tra i tech leader sul palco. Ti tengo un posto?

**[Tier A · 1:1 · track Languages & Architectures] L002 Davide Aru (VP Engineering, Helix Mobility)**
> Ciao Davide, ho visto che avete rilasciato in open source il vostro motore di routing in Go: bella mossa per la community. A DevReach 2026 (la conferenza, due giorni) la track Languages & Architectures e' piena di chi ragiona su open source e performance, e visto che organizzi anche il meetup Go ci staresti benissimo. Ti riservo un posto?

**[Tier A · 1:1 · track AI/ML] L012 Federico Neri (CTO, Saliva Health)**
> Ciao Federico, far approvare un modello di triage sintomi come dispositivo medico e' un traguardo serio: l'AI in sanita' di solito si ferma molto prima. A DevReach 2026 la track AI/ML tocca proprio governance e modelli in produzione, e il tuo punto di vista da founder tecnico varrebbe parecchio. Ti riservo un posto?

**[Tier A · RECUPERO drop-off ALTO · track Languages & Architectures] L010 Tomas Varga (Director of Engineering, Northpeak)**
> Ciao Tomas, intanto complimenti per la riscrittura del core di pagamento con il -40% di latenza: numeri cosi' si vedono di rado. Ti scrivo perche' eri registrato a DevReach 2026 e non vorrei ti sfuggisse: track Languages & Architectures, c'e' un confronto serio su performance e architetture critiche. Ti confermo il posto?

**[Tier B · sequenza Waalaxy · track Cloud & Architectures] L007 Anna Castelli (Solutions Architect, Cloudbridge)**
> Ciao Anna, ho letto del vostro framework di FinOps per il controllo dei costi cloud: tema sempre piu' caldo. A DevReach 2026 (la conferenza, due giorni), track Cloud & Architectures, ci sono sessioni hands-on proprio su questo. Penso ti possa interessare: ti mando l'agenda?

**[Tier B · RECUPERO drop-off ALTO · track Data Engineering] L003 Elena Fabbri (Engineering Manager, Banca Aurea)**
> Ciao Elena, bentornata! Ho visto la vostra nuova piattaforma dati per il rischio credito in tempo reale: sono i temi della track Data Engineering. Eri con noi l'anno scorso e ti eri registrata anche stavolta, volevo assicurarmi che avessi il posto confermato per la conferenza. Te lo blocco?

**[Tier B · sequenza Waalaxy · track AI/ML] L004 Samuel Okoro (Staff Engineer, Pomodoro AI)** `[SEGNALE DA RICERCARE]`
> Ciao Samuel, ho visto che mantieni una libreria ML piuttosto nota: l'open source lo vivi davvero. A DevReach 2026 (la conferenza, due giorni) la track AI/ML e' pensata per chi costruisce, non per chi guarda le slide. Ti mando l'agenda?
> ⚠️ *Nessun progetto recente di Pomodoro AI nel dato. Personalizzazione costruita sul segnale OSS, non sull'azienda. Un complimento su un rilascio reale alzerebbe la resa: cercarlo a mano prima dell'invio.*

*(Gli altri Tier A — L014 Ilaria Conti, L009 Sara Moretti, L017 Andrea Lombardi — seguono lo stesso schema, ciascuno ancorato al proprio segnale.)*

### 4. SPONSOR (EXTRA MILE) — SCORING & MESSAGGI

**Tier A (priorita' commerciale):**

**[S001 Vectorly · Head of Developer Relations · vende ai dev + assume]**
> Ciao Giorgia, complimenti per il lancio del vostro database vettoriale gestito per il RAG: e' esattamente cio' che cercano i team che stanno portando l'AI in produzione. A DevReach 2026 ci sono oltre 250k developer della community: per un prodotto cosi' dev-first e' il palco naturale per farvi provare e per assumere. Vi va un confronto sulle opzioni sponsor?

**[S002 Forgepipe · Co-founder & CEO · seed fresco]**
> Ciao Marco, complimenti per il round seed da 4M sulla piattaforma CI/CD: e' il momento giusto per farsi conoscere dalla community giusta. DevReach 2026 mette il vostro tool davanti a developer che vivono di CI/CD ogni giorno. Posso girarti il pacchetto sponsor con i numeri di reach?

**[S003 Banca Aurea · Head of Tech Talent · Tier B, assume forte]**
> Ciao Paola, ho visto che aprite un hub tech a Roma con 80 assunzioni: trovare quei profili e' la sfida vera. A DevReach 2026 incontrate dal vivo migliaia di developer, e c'e' uno spazio sponsor pensato per l'employer branding e il recruiting. Ti mando come funziona?

⚠️ **S006 Reti Spa** scartato (Tier Out): non vende ai dev, non assume, nessun segnale recente. Non investire tempo 1:1.

### 5. ALERT DROP-OFF
- 🔴 **L010 Tomas Varga** (Tier A, Director): 22 giorni di silenzio, 0 aperture. Profilo piu' costoso da perdere. Azione: messaggio di recupero sopra, a mano, entro 24h.
- 🔴 **L003 Elena Fabbri** (Tier B, past attendee): 25 giorni di silenzio. Azione: "bentornata" che lega l'edizione passata al segnale aziendale di oggi.
