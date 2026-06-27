# Examples

- [`sample-output.md`](sample-output.md) — output completo su `data/leaders.csv` (12 tech leader) e `data/sponsors.csv` (6 aziende sponsor). Mostra: blocco `<calcoli_interni>` verificabile, scoring + track + drop-off per i leader, messaggi pronti ancorati al segnale reale, il fallback `[SEGNALE DA RICERCARE]` quando il dato manca, e il fronte sponsor (extra mile).

### Come riprodurlo
1. Apri [https://claude.ai](https://claude.ai), nuova conversazione.
2. Incolla [`docs/system-prompt.md`](../docs/system-prompt.md).
3. Incolla [`data/leaders.csv`](../data/leaders.csv) (e [`data/sponsors.csv`](../data/sponsors.csv) per il fronte sponsor).
4. Claude genera il report in ~20 secondi.
