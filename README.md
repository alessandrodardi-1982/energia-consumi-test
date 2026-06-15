[README_energia.md](https://github.com/user-attachments/files/28949518/README_energia.md)
# ⚡ Analisi Consumi Energetici — Termoflex Srl

Dashboard interattiva con AI integrata per il monitoraggio e la diagnosi dei consumi energetici in un impianto industriale.

**→ [Apri la dashboard](https://energia-consumi.netlify.app/dashboard_energia.html)**

---

## Il problema

Molte aziende industriali hanno i contatori, i quadri elettrici e i dati — ma non li leggono. I consumi vengono registrati, fatturati e archiviati. Le anomalie passano inosservate per mesi: un compressore lasciato acceso nel weekend, un macchinario che non si spegne di notte, un fermo impianto con i carichi ancora attivi.

Il costo di questa disattenzione non è trascurabile. In un impianto medio, il 10–15% del consumo annuo è recuperabile semplicemente correggendo comportamenti e automazioni già esistenti.

---

## La soluzione

Una dashboard web che trasforma i dati grezzi di consumo in informazioni operative chiare:

- **Trend mensile per reparto** — dove va l'energia, mese per mese
- **Anomalie evidenziate automaticamente** — picchi, sprechi, fermi non dichiarati
- **Analisi AI on-demand** — un clic invia i dati a Claude, che restituisce una diagnosi con impatto economico e azioni correttive prioritizzate

---

## Cosa mostra la dashboard

| Sezione | Contenuto |
|---|---|
| KPI header | Consumo totale, costo annuo, anomalie rilevate, risparmio potenziale |
| Trend mensile | Grafico stacked bar per 4 reparti su 12 mesi |
| Anomalie | 3 eventi anomali con reparto, data, scostamento e descrizione tecnica |
| Ripartizione | Barre percentuali + doughnut chart per reparto |
| Stagionalità | Grafico refrigerazione (picco estivo) e compressori (anomalia marzo) |
| Analisi AI | Diagnosi Claude con valutazione, impatto economico e piano azioni |

---

## Le anomalie nel dataset

Il dataset 2023 di Termoflex Srl contiene tre anomalie realistiche inserite per illustrare la logica di analisi:

**1. Picco notturno — Produzione, 14 luglio ore 02:00**
Consumo +109% rispetto al profilo notturno atteso. Possibile macchinario non spento o avvio automatico non autorizzato.

**2. Spreco weekend — Compressori, sabato 18 marzo**
Compressori a pieno regime (+261%) con impianto produttivo fermo. Valvole di by-pass probabilmente rimaste aperte.

**3. Fermo non dichiarato — Produzione, 23–24 ottobre**
Stop pianificato ma consumi invariati rispetto ai giorni lavorativi (+1025%). Macchinari lasciati accesi durante lo stop.

Risparmio potenziale stimato se le tre anomalie vengono corrette sistematicamente: **~18.000 €/anno**.

---

## Perché questo progetto

Ho lavorato per anni nella gestione di impianti industriali — aria compressa, refrigerazione, coordinamento tecnico. I costi energetici erano sempre presenti nelle discussioni con i clienti, ma raramente c'era uno strumento per leggerli in modo strutturato.

Questo progetto nasce da quella lacuna: tradurre dati già disponibili in un formato che permetta di prendere decisioni operative concrete, con il supporto dell'AI per l'analisi contestuale.

---

## Stack tecnico

| Strumento | Ruolo |
|---|---|
| HTML / CSS / JS | Dashboard single-file, zero dipendenze server |
| Chart.js | Grafici trend, ripartizione, stagionalità |
| Claude API (`claude-sonnet-4-6`) | Analisi AI on-demand dei consumi |
| Netlify Functions | Proxy serverless per la chiave API (mai nel browser) |
| Python | Generazione del dataset sintetico |

---

## Note sul dataset

I dati sono **sintetici ma realistici**: generati via script Python con profili di consumo orari per 4 reparti (Produzione, Compressori, Refrigerazione, Uffici) su 12 mesi, con variazioni stagionali coerenti e anomalie inserite in modo controllato.

Il metodo è applicabile direttamente a dati reali esportati da sistemi di building management (BMS), contatori smart o fogli di raccolta manuale in formato CSV.

---

## Autore

**Alessandro Dardi** — Operations & Digital Automation · Bologna
[Portfolio](https://alessandro-dardi.netlify.app) · [LinkedIn](https://www.linkedin.com/in/alessandro-dardi/)
