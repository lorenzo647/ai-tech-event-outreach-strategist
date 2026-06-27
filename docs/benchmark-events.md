# Benchmark - Audience di eventi tech B2B (Italia/EU 2026)

> Soglie di riferimento usate dal sistema per dare un giudizio a semaforo sulla qualita' dell'audience e sui rischi di drop-off. Sono valori indicativi, calibrati sul mondo delle conferenze per sviluppatori e leader tech in Italia ed Europa. Vanno ricalibrati per eventi di scala o verticale diversi.

## 1. Composizione dell'audience (mix di seniority)

Per una conferenza che vuole figure decisionali in sala, un bacino "in target" dovrebbe avere:

| Segmento | Quota sana del bacino lavorato | Lettura |
|---|---|---|
| Tier A (C-level, VP, decisori core) | >= 20% | 🟢 forte se sopra, 🔴 debole se sotto il 10% |
| Tier A + Tier B insieme | >= 50% | sotto, il bacino e' troppo "junior" per l'obiettivo |
| Out (fuori ICP) | <= 25% | sopra, la lista e' poco profilata, rivedere le fonti |

## 2. Conversione di funnel (benchmark indicativi)

| Passaggio | Benchmark sano | Note |
|---|---|---|
| contacted -> replied (figure senior) | 15-25% | sotto il 10% = messaggio o targeting da rivedere |
| replied -> registered | 40-60% | la qualita' del follow-up pesa molto |
| registered -> confirmed | 60-75% | il pezzo dove si gioca il no-show |
| confirmed -> attended (in presenza) | 70-85% | sotto, rivedere reminder e logistica |

## 3. Tasso di no-show (assente dopo registrazione)

| Tipo evento | No-show fisiologico | Soglia di allarme |
|---|---|---|
| Evento B2B gratuito in presenza | 40-50% | > 55% = problema di engagement |
| Evento B2B a pagamento in presenza | 15-25% | > 30% = problema di engagement |
| Evento ibrido / online | 55-70% | atteso alto, puntare sulla qualita' non sul numero |

Il dato chiave: su un evento gratuito, **circa un registrato su due non si presenta**. Per questo il sistema stima la partecipazione attesa come `confirmed + (registered * 0.6)` e tratta la riduzione del no-show come leva di valore, non come dettaglio.

## 4. Canali di provenienza (fertilita' attesa sui profili senior)

| Fonte | Qualita' media del contatto | Sforzo per contatto |
|---|---|---|
| referral | alta | basso |
| inbound | alta | basso |
| past_attendee | media-alta | basso |
| partner_list | media | medio |
| scraping | bassa-media | alto (va profilato) |

Implicazione operativa: i Tier A che arrivano da `scraping` vanno verificati a mano prima di un contatto diretto; quelli da `referral`/`inbound` si possono lavorare subito in 1:1.

## 5. Segnali di rischio drop-off (per registered/confirmed)

Pesano sul rischio di no-show, in ordine di gravita':
1. nessuna apertura email recente (`email_opens` = 0)
2. ultimo contatto oltre 3 settimane fa (`last_touch_days` > 21)
3. ancora `registered` e non `confirmed` a ridosso dell'evento
4. partecipante dall'estero senza conferma logistica

Attenuante forte: i contatti con `community_signal` speaker/organizer/past_attendee hanno storicamente no-show piu' basso e vanno considerati piu' stabili.
