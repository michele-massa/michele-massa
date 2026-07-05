# Tuscany Climbing — guida alle falesie della Toscana

> Concept v0.1 · bozza di lavoro · luglio 2026

## 1. L'idea in una frase

Una guida web, veloce e curata, a **tutte le falesie della Toscana**: dove sono, come ci si
arriva, quando ha senso andarci e che cosa si scala — con i **gradi allineati a Vertical Life**,
che è la fonte di riferimento usata dalla community.

## 2. Perché

Le informazioni sulle falesie toscane oggi sono sparse tra guide cartacee (ottime ma statiche),
siti locali datati, forum e app. Manca un punto d'ingresso unico, in italiano e inglese, pensato
sia per chi scala in zona sia per chi viene in vacanza ("tuscany climbing" è una ricerca reale
di chi pianifica un viaggio). Il valore del sito non è duplicare i topo — è **orientare**:
scegliere la falesia giusta per stagione, grado, esposizione e logistica.

## 3. A chi si rivolge

- **Climber locali** (Pisa, Lucca, Firenze, Livorno…): "domani pomeriggio dove vado?"
- **Climber in viaggio**: "una settimana in Versilia, cosa c'è dal 6a al 7a all'ombra?"
- **Principianti e famiglie**: falesie con avvicinamento corto, base comoda, gradi facili.

## 4. I gradi: Vertical Life come fonte

Decisione chiave del progetto: **i gradi non li inventiamo né li mediamo noi** — si riporta
la valutazione pubblicata su Vertical Life (scala francese), citandola come fonte.

Come farlo correttamente:

1. **Niente scraping.** I topo di Vertical Life sono opera di autori locali e sono coperti da
   licenza; il sito inoltre non espone un'API pubblica. I dati si inseriscono a mano (o tramite
   futura partnership), verificandoli sull'app.
2. **Ogni via e ogni falesia porta il campo `fonte`** con link alla zona Vertical Life
   corrispondente e la **data di ultima verifica** (`ultima_verifica`). Se un grado è
   dibattuto, si riporta quello di Vertical Life e basta — la discussione sta lì.
3. **Attribuzione visibile** nel sito: "I gradi seguono le valutazioni pubblicate su
   Vertical Life" + link. Questo è anche un servizio al lettore: dal nostro sito si salta
   direttamente al topo ufficiale per il dettaglio tiro per tiro.
4. **Prospettiva**: contattare Vertical Life per una partnership (embed dei topo, link
   affiliati all'acquisto delle guide digitali). Il sito porta loro traffico qualificato,
   quindi la proposta ha senso per entrambi.

## 5. Struttura del sito

- **Home** — mappa + elenco falesie con filtri (provincia, grado, esposizione, stagione,
  avvicinamento, adatta a famiglie).
- **Pagina falesia** — descrizione, accesso e parcheggio, esposizione/quota/stagioni,
  settori, tabella vie con gradi (fonte Vertical Life), distribuzione dei gradi,
  avvertenze (divieti, nidificazione, frane), link al topo Vertical Life.
- **Pagina zona** — raggruppamenti naturali: Camaiorese, Alta Versilia/Apuane, Valdinievole,
  Maremma, Elba…
- **Pagine di servizio** — "Come leggere i gradi", "Etica e accessi", "Chi siamo", disclaimer.

## 6. Modello dati

Un file/record per falesia (vedi `data/falesie.json` per lo schema completo e dati di esempio):

```jsonc
{
  "id": "candalla-bassa",
  "nome": "Candalla Bassa",
  "zona": "Camaiorese",
  "comune": "Camaiore",
  "provincia": "LU",
  "coordinate": { "lat": 43.957, "lng": 10.321, "precisione": "indicativa" },
  "roccia": "calcare",
  "esposizione": "N",
  "quota_m": 150,
  "avvicinamento_min": 10,
  "stagioni": ["primavera", "estate", "autunno"],
  "famiglie": false,
  "stile": ["strapiombo", "continuità"],
  "settori": [
    { "nome": "…", "vie": [{ "nome": "…", "grado": "7a", "lunghezza_m": 25 }] }
  ],
  "gradi": {
    "fonte": "Vertical Life",
    "url": null,               // link alla zona VL, da inserire
    "ultima_verifica": null,   // data verifica gradi sull'app
    "min": "6a",
    "max": "8b"
  }
}
```

Note sul modello:

- `gradi.min`/`max` e il conteggio vie stanno **denormalizzati** sulla falesia per i filtri;
  la verità fine sta nelle vie dei settori.
- Le coordinate portano un campo `precisione` — per gli accessi delicati si pubblica il
  **parcheggio**, non la parete, ed eventualmente si rimanda alle indicazioni locali.
- Un campo `avvisi` (array) per divieti temporanei, chiusure per nidificazione, frane.

## 7. Stack tecnico proposto

- **Sito statico** (Astro o Next.js in export statico): niente backend, gratis su GitHub
  Pages / Netlify / Vercel, velocissimo, SEO ottima.
- **Dati in JSON/Markdown nel repo**: ogni falesia è un file, le modifiche passano da PR —
  il versionamento dei gradi viene gratis con git.
- **Mappa**: Leaflet/MapLibre + OpenStreetMap (gratuito, nessuna API key).
- **i18n**: italiano prima, inglese subito dopo (il pubblico "tuscany climbing" è straniero).
- **Zero login, zero database** nell'MVP. Contributi via GitHub o form → email.

## 8. Roadmap

| Fase | Contenuto | Fatto quando |
|---|---|---|
| 0 — Concept | questo documento + prototipo statico | ✅ (questa cartella) |
| 1 — MVP | 10–15 falesie della Versilia/Camaiorese verificate su Vertical Life, mappa, filtri, IT | sito online |
| 2 — Copertura | tutte le zone principali (Apuane, Valdinievole, Maremma, Elba), EN | ~50 falesie |
| 3 — Community | segnalazioni condizioni/avvisi, contatto con Vertical Life per partnership | primo contributo esterno |

## 9. Prototipo

In `prototype/index.html` c'è un **prototipo navigabile e self-contained** (nessuna dipendenza):
elenco falesie con filtri, scheda di dettaglio con settori, tabella vie, distribuzione dei
gradi e attribuzione Vertical Life. I dati dentro il prototipo sono **dimostrativi**
(falesie reali, ma numeri e vie da verificare sull'app prima di pubblicare qualsiasi cosa).

## 10. Cose da decidere

- **Nome e dominio**: "Tuscany Climbing" è chiaro per il pubblico estero
  (tuscanyclimbing.com?); alternativa italiana tipo "Toscana Verticale".
- Licenza dei **nostri** contenuti (descrizioni, foto): CC BY-NC-SA?
- Foto: proprie o con permesso — mai prese dai topo altrui.
