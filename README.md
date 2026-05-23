# MusicTrack — Website

Sito ufficiale di **MusicTrack**, studio manager per insegnanti di canto e musica.

🔗 **Live:** [musictrack.it](https://musictrack.it)

---

## Stack

Sito statico ospitato su **GitHub Pages**, con dominio custom `musictrack.it` (CNAME).
Nessun build step: i file HTML sono pubblicati così come sono. Le pagine `index.html`, `Prodotto.html` e `Storie.html` includono **React + ReactDOM + Babel** inline per alcuni componenti interattivi (caroselli, tilt, magnetic buttons). Le altre pagine sono HTML+CSS puro.

## Pagine

| File | URL | Schema strutturato |
| --- | --- | --- |
| `index.html` | `/` | Organization · WebSite · SoftwareApplication |
| `Prodotto.html` | `/Prodotto.html` | SoftwareApplication + Breadcrumb |
| `Per insegnanti di canto.html` | `/Per%20insegnanti%20di%20canto.html` | Service + Breadcrumb |
| `Per scuole di musica.html` | `/Per%20scuole%20di%20musica.html` | Service + Breadcrumb |
| `Storie.html` | `/Storie.html` | WebPage + Breadcrumb |
| `Chi siamo.html` | `/Chi%20siamo.html` | AboutPage + Organization |
| `Domande frequenti.html` | `/Domande%20frequenti.html` | **FAQPage (22 Q&A)** + Breadcrumb |
| `Beta.html` | `/Beta.html` | WebPage + Breadcrumb |
| `Scrivici.html` | `/Scrivici.html` | ContactPage + ContactPoint |

## SEO & GEO

Ogni pagina include:

- `meta description` univoca (~155 char)
- `link rel="canonical"` su `https://musictrack.it`
- **Open Graph** + **Twitter Card** completi (immagine 1116×600)
- **JSON-LD** strutturati (vedi tabella sopra)
- `meta robots: index, follow, max-image-preview:large`
- Favicon (16, 32, apple-touch 180)

A livello sito:

- `robots.txt` — allowlist esplicita per GPTBot, ClaudeBot, PerplexityBot, OAI-SearchBot, Google-Extended, Applebot-Extended, Bytespider, CCBot, ecc.
- `sitemap.xml` — tutte e 9 le pagine
- `llms.txt` — riassunto markdown del sito per i crawler LLM (convenzione GEO)

## Asset

| File | Note |
| --- | --- |
| `og-image.png` | 1116×600 — immagine condivisa OG/Twitter |
| `favicon-32.png`, `favicon-16.png`, `apple-touch-icon.png` | Generati da `favicon-mt.png` (sorgente 1024×1024, non versionata) |
| `edona.jpg`, `miriam.jpg` | Ritratti fondatrici — 800×800 JPEG q85 (~170 KB) |
| `CNAME` | `musictrack.it` (dominio canonico, non-www) |

## Sviluppo locale

Apri i file `.html` direttamente nel browser, oppure servi la cartella con un mini server:

```bash
# da dentro la cartella del progetto
python3 -m http.server 8000
# poi http://localhost:8000/
```

Modifiche al CSS e all'HTML statico sono visibili al refresh. Le sezioni React-driven (hero, caroselli) richiedono il file completo: nessun watcher/transpile separato.

## Deploy

Push su `main` → **GitHub Pages** ricompila automaticamente in 1-2 minuti.

```bash
git add <files>
git commit -m "..."
git push
```

DNS `musictrack.it` → GitHub Pages via il `CNAME` versionato nella root.

## Convenzioni

- File HTML con nome leggibile in italiano (es. `Domande frequenti.html`). Le URL sono di conseguenza encoded con `%20`. Se in futuro si vuole passare a slug puliti (`/domande-frequenti`), serve anche un piano di redirect.
- Email canonica: `hello@musictrack.it`
- Colore brand: `#8264BE` (viola)
- Font: Outfit (sans) + Cormorant Garamond (serif)
