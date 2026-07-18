# ◆ Noch zu holen

Meine komplette Kaufliste als Website — 209 Wünsche über neun Kategorien,
sortiert, priorisiert, abhakbar. Gebaut mit [Claude Code](https://claude.com/claude-code).

![Screenshot der Website](assets/images/site-preview.png)

## Öffnen

`website/index.html` im Browser öffnen — fertig. Kein Server, kein Build,
keine Installation. Die Ordnerstruktur muss zusammenbleiben, damit die
lokalen Produktbilder aus `assets/` laden.

## Was die Seite kann

- **Abhaken mit Gedächtnis** — Haken werden im Browser (localStorage) gespeichert
  und überleben Neuladen. Fortschrittsring im Hero, Zähler und Balken je Kategorie.
- **Undo** — jeder Haken lässt sich direkt über den Toast rückgängig machen.
- **Filter** — Erledigte ausblenden, nach Priorität filtern (Muss / Nice / Traum),
  nach Preis sortieren, Budget-Grenze setzen („max €").
- **Suche** über Titel, Notizen, Marken und Gruppen (`/` fokussiert die Suche).
- **Produktbilder** — 159 lokal gespeichert (`assets/images/products/`), Rest lädt
  von den Shop-Servern; Fallback-Kette lokal → remote → Monogramm.
- **Lightbox** mit Blättern (`←`/`→`), Abhaken direkt im Bild.
- **Gruppen** — Hauptprodukt + Zubehör, Alternativen („noch nicht entschieden"),
  Serien-Pakete; einzeln oder alle auf einmal aufklappbar.
- **Große Träume** — Projektansicht, z. B. die Zimmer-Umgestaltung nach Bereichen.
- **Stand sichern / laden** — Abhak-Stand als JSON exportieren und wieder importieren.
- **Drucken** — reduzierte Einkaufsliste (nur offene Einträge) über den Drucken-Button.

## Projektstruktur

```
├── README.md
├── copy/
│   └── brand-kit.md          # Design-Kit: Farben, Typo, Ton, Sektionen
├── assets/
│   ├── images/
│   │   ├── products/         # lokal gespeicherte Produktbilder (nach item.id)
│   │   └── site-preview.png
│   ├── references/           # generierte Hero-/Mood-Referenzbilder
│   └── videos/
└── website/
    └── index.html            # die komplette App — eine Datei, kein Backend
```

## Technik

Eine einzige HTML-Datei mit eingebettetem CSS/JS, ohne Framework und ohne Backend.
Datenquelle ist das `items`-Array in `index.html` — Änderungen an der Liste laufen
direkt über diese Datei. Design nach `copy/brand-kit.md`: warmes Fast-Schwarz,
Amber-Akzent, Fraunces / Inter / JetBrains Mono, Filmkorn, Scroll-Reveal —
alles respektiert `prefers-reduced-motion`.
