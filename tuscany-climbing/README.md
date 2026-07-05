# Tuscany Climbing — guida alle falesie della Toscana

Guida web alle falesie della Toscana: dove sono, come si arriva, quando andarci e
cosa si scala — con i **gradi allineati a [Vertical Life](https://www.vertical-life.info/)**,
citata come fonte per ogni falesia.

> ⚠️ **Prototipo (v0.1).** Le falesie sono reali, ma conteggi, vie e distribuzioni
> dei gradi sono **dati dimostrativi** da verificare su Vertical Life prima della
> pubblicazione. Le coordinate sono indicative e puntano alla zona, non alla parete.

## Contenuto del repository

| Percorso | Cosa contiene |
|---|---|
| `CONCEPT.md` | Il concept del progetto: visione, pubblico, struttura del sito, modello dati, stack tecnico e roadmap |
| `data/falesie.json` | Schema dati e falesie di esempio (8 falesie reali, dati dimostrativi) |
| `prototype/index.html` | Prototipo navigabile, file unico senza dipendenze — apri in un browser |

## I gradi: Vertical Life come fonte

I gradi (scala francese) **riportano le valutazioni pubblicate su Vertical Life**,
non le inventiamo né le mediamo. Regole del progetto:

- **Niente scraping.** I topo di Vertical Life sono opera di autori locali e sono
  coperti da licenza; il sito non espone un'API pubblica. I dati si inseriscono a
  mano, verificandoli sull'app.
- Ogni falesia porta **fonte, link alla zona Vertical Life e data di ultima verifica**.
- **Attribuzione visibile** in tutto il sito, con link al topo ufficiale per il
  dettaglio tiro per tiro.

## Provare il prototipo

Apri `prototype/index.html` in un browser (doppio clic sul file) — è completamente
autonomo, nessuna installazione. Filtri per provincia, esposizione, fascia di grado
e "adatte a famiglie"; scheda di dettaglio con settori, vie e distribuzione dei gradi.

## Stato e roadmap

Vedi `CONCEPT.md` § Roadmap. In breve: **Fase 0** (concept + prototipo) ✅ · **Fase 1**
MVP con ~10–15 falesie della Versilia verificate · **Fase 2** copertura di tutte le
zone principali (Apuane, Valdinievole, Maremma, Elba) e versione inglese.

## Avvertenza

L'arrampicata è un'attività pericolosa. Le informazioni qui raccolte non
sostituiscono il giudizio in loco: verifica sempre condizioni, divieti e chiodatura.
