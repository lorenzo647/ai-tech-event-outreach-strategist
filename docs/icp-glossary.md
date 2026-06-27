# Glossario - ICP & Audience di eventi tech

Definizioni operative per allineare la terminologia. Servono a leggere l'output del sistema senza ambiguita'.

**ICP (Ideal Customer Profile).** Il profilo del partecipante ideale per l'evento. Qui non e' un "cliente" che compra, ma il **decisore tech** che si vuole portare in sala: chi influenza scelte di stack, budget e adozione tecnologica. L'ICP e' definito dalla combinazione di seniority, rilevanza del ruolo, tipo di azienda e appartenenza alla community.

**ICP Fit Score (0-100).** Punteggio sintetico che misura quanto un contatto e' vicino all'ICP. Calcolato in modo deterministico (vedi `system-prompt.md`) sommando quattro componenti: seniority, rilevanza del ruolo, fit dell'azienda, segnale di community.

**Tier (A / B / C / Out).** Fascia di priorita' derivata dallo score. Tier A = lavorare a mano in 1:1; Tier B = nurture semi-personalizzato; Tier C = automazione; Out = fuori target, non investire tempo umano.

**Seniority.** Livello gerarchico/decisionale del contatto, non anni di esperienza. Un C-level pesa piu' di un Senior IC perche' decide, non solo perche' e' bravo.

**Rilevanza del ruolo.** Quanto il ruolo e' vicino alle decisioni tecnologiche core dell'evento. Un CTO o un VP Engineering pesano piu' di un QA Engineer, a parita' di seniority formale.

**Community signal.** Segnale che il contatto e' parte attiva della community tech: e' gia' stato speaker, organizza meetup, mantiene progetti open source, e' un past attendee o un iscritto newsletter. E' un proxy di interesse reale e, sui registrati, e' un attenuante del rischio no-show.

**Engagement stage (funnel).** Lo stadio del contatto nel percorso: identified (individuato) -> contacted (contattato) -> replied (ha risposto) -> registered (iscritto) -> confirmed (ha confermato la presenza).

**Drop-off / no-show.** L'abbandono tra registrazione e partecipazione effettiva. E' il punto dove un evento gratuito perde piu' valore: il sistema lo tratta come metrica di prima classe e produce un playbook dedicato per ridurlo.

**High-touch vs automazione.** High-touch = contatto umano diretto e personalizzato, riservato ai Tier A. Automazione = sequenze CRM segmentate, per Tier C e per la parte ripetitiva. Il senso del ruolo e' mettere il tempo umano dove rende di piu'.

**Stima di partecipazione attesa.** Proiezione prudenziale dei presenti reali, calcolata come `confirmed + (registered * 0.6)`, dove 0.6 e' una resa conservativa dei soli registrati non ancora confermati.

---

## Aggiunte v2 (Message Engine)

**company_recent_signal.** L'ultimo progetto o notizia reale e recente dell'azienda del contatto, con fonte e data (`signal_source`). E' la materia prima del complimento di apertura. Se manca, il sistema non lo inventa.

**Regola di grounding.** Il complimento puo' nascere solo da un segnale verificato. Mai dedurre o inventare un progetto. In assenza di segnale: personalizzazione neutra + tag `[SEGNALE DA RICERCARE]`.

**Message Engine.** Il modulo che, per ogni contatto Tier A/B, scrive il messaggio in tre tempi: aggancio (complimento ancorato) -> ponte all'evento (giornata giusta) -> CTA leggera.

**ICP per giornata.** L'evento e' multi-giornata: l'ICP cambia per giorno, quindi l'output assegna a ogni contatto non solo un tier ma la giornata piu' adatta (Summit per i decisori, Builders Lab per i lead tecnici, ecc.).

---

## Aggiunte v3 (conferenza tech B2B: sponsor & pipeline)

**Sponsor Fit Score.** Punteggio dell'azienda come potenziale sponsor: vende ai developer (+35), assume tech (+25), dimensione/budget, segnale recente (+20). Tier A = priorita' commerciale.

**Decisore sponsor.** La persona giusta dentro l'azienda dipende dal motivo: se vende ai dev -> Head of DevRel/Marketing; se assume -> Head of Tech Talent.

**Track affinity.** Assegnazione del contatto alla track della conferenza piu' affine al suo tech_domain, usata come gancio nel messaggio.

**Pipeline & collante.** Sales Navigator -> Waalaxy/Phantombuster -> CSV/Sheets -> tool -> Waalaxy (outreach) + HubSpot (CRM destinazione). Il collante di automazione e' n8n (alternative: Zapier, Make). HubSpot ha API reale (push fattibile, in roadmap); Waalaxy no (solo export).
