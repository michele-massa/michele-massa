# Checklist operativa — Simulatore PAC in prima pagina

Spunta le voci man mano. L'ordine è per impatto: le prime voci sbloccano le successive.

## Settimana 1 — Dati e fondamenta tecniche

- [x] ~~Google Search Console: verifica proprietà~~ → **già attiva**
- [x] ~~Title e meta description~~ → **già ottimizzati** (in SERP: "Simulatore PAC Online Gratuito | Calcola il tuo Piano di …")
- [ ] **Analisi GSC** (il vero primo passo): Rendimento → filtro pagina `/simulatore-pac/` → ultimi 3 mesi → esporta le query con posizione media, impression e CTR. Le query in **posizione 8–20** sono i bersagli immediati
- [ ] In GSC → Sitemap: verifica che la sitemap sia inviata e letta senza errori
- [ ] In GSC → Pagine: verifica quante pagine del sito risultano indicizzate
- [ ] **Canonical** presente e corretto (vedi `meta-tag.html`)
- [ ] Test **PageSpeed Insights** mobile: https://pagespeed.web.dev → obiettivo punteggio ≥ 80 e Core Web Vitals verdi (se il simulatore è una web-app JS pesante, valuta caricamento differito degli script non critici)
- [ ] La pagina deve essere **usabile da mobile** (la maggioranza delle ricerche "simulatore pac" è da smartphone)

## Settimana 1–2 — On-page

- [ ] Aggiungi l'**H1** e il **contenuto sotto il simulatore** (vedi `contenuti-on-page.md`) — verifica prima i punti `[VERIFICA]`
- [ ] Aggiungi i **dati strutturati** (vedi `schema-jsonld.html`) e valida su https://search.google.com/test/rich-results
- [ ] Crea l'**immagine Open Graph** 1200×630 (screenshot del simulatore + logo) e caricala all'URL indicato nei meta tag
- [ ] **Alt text** su tutte le immagini della pagina (es. "grafico andamento PAC anno per anno")
- [ ] **Box autore + disclaimer** in fondo alla pagina (E-E-A-T: fondamentale su temi finanziari)
- [ ] Crea/verifica le pagine **Chi siamo**, **Contatti** e **Privacy** del sito (Google le usa come segnale di affidabilità sui siti finanziari)

## Settimana 2–4 — Link interni e contenuti di supporto

- [ ] Link dalla **homepage** al simulatore con anchor descrittiva (es. "Simulatore PAC gratuito")
- [ ] Link al simulatore da **ogni articolo/pagina esistente** del sito dove ha senso
- [ ] Pubblica gli **articoli di supporto** (ognuno con link al simulatore):
  - [ ] "Quanto rende un PAC di 100 € al mese per 10, 20 e 30 anni"
  - [ ] "SWR: quanto puoi prelevare ogni mese senza esaurire il capitale"
  - [ ] "PAC o PIC: cosa conviene e quando"
  - [ ] "PAC a leva: come funziona e quali rischi comporta"
- [ ] Aggiorna la **scheda Google Play** dell'app: assicurati che il link al sito punti esattamente a `https://primaltoinvestimenti.it/simulatore-pac/`

## Mese 1–3 — Off-page (autorità)

- [ ] **Instagram @primalto_investimenti**: link al simulatore in bio + post/reel che mostrano simulazioni concrete ("100 € al mese per 20 anni: ecco cosa succede")
- [ ] Contatta i siti che pubblicano **rassegne di simulatori PAC** (es. l'articolo di nevist.it "Simulazione piano di accumulo: come si calcola e dove") proponendo l'inserimento del tuo — è il link più facile da ottenere
- [ ] Partecipa (senza spam) a discussioni su PAC in community italiane: r/ItaliaPersonalFinance, FinanzaOnline — condividi il simulatore solo dove le regole lo consentono e quando risponde a una domanda reale
- [ ] Valuta un **video YouTube** ("Come simulare un PAC gratis") con link in descrizione: i video ranking anche in SERP
- [ ] Cerca directory/aggregatori di **strumenti finanziari gratuiti** italiani e richiedi l'inserimento

## Monitoraggio continuo

- [ ] Ogni 2 settimane: GSC → Rendimento → filtra pagina `/simulatore-pac/` → osserva query, impression, **posizione media** e CTR
- [ ] Il title attuale è già buono: solo se dopo 4–6 settimane il CTR resta < 2-3% sulle query non-brand, testa una variante (vedi `meta-tag.html`), una alla volta
- [ ] Collega **Google Search Console a Windsor.ai** (dove è già collegato Instagram): così i dati di posizionamento sono analizzabili anche nelle prossime sessioni con Claude
- [ ] Obiettivi: entro 2 mesi in top 20 per le long-tail ("simulatore pac a leva", "quanto rende un pac di 100 euro al mese"); entro 4–6 mesi in top 10 per "simulatore pac gratis" / "simulatore pac etf"; poi si attacca "simulatore pac"
