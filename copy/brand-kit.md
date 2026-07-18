# Design-Kit — „Noch zu holen"

> Kein Marken-Projekt: Diese Seite ist eine professionelle Demo, die zeigt, was sich mit
> Claude Code bauen lässt — aufgehängt an einem echten, persönlichen Anwendungsfall:
> eine Checkliste mit allem, was ich mir noch kaufen will.
> Publikum der Demo: meine Eltern.

---

## 1. Projektname

**Noch zu holen** — als Wortmarke: `NOCH ZU HOLEN` (gesetzt in der Display-Schrift, gesperrt).

Kurz, deutsch, selbstironisch-ehrlich. Kein Kunstname, keine Fantasiemarke — der Name sagt
exakt, was die Seite ist. Das wirkt souveräner als ein aufgesetztes Startup-Branding.

## 2. Slogan

**„Alles, was noch fehlt. An einem Ort."**

Alternative für den Hero, wenn mehr Kontext gut tut:
„Meine komplette Kaufliste — sortiert, priorisiert, abhakbar."

## 3. Positionierung

Eine persönliche, interaktive Kauf-Checkliste als hochwertige One-Page-Webanwendung.
Kein Shop, kein Produkt zum Verkaufen — das „Produkt" ist die Seite selbst:
Sie demonstriert, dass aus einer simplen Liste eine Website entstehen kann, die aussieht
und sich anfühlt wie das Werk einer teuren Agentur. Positionierung gegenüber dem
Demo-Publikum (Eltern): „Das hier hat ein Werkzeug gebaut, mit dem ich einfach reden kann."

## 4. Zielgruppe

- **Primär:** Meine Eltern — technisch interessiert, aber keine Entwickler. Die Seite muss
  ohne Erklärung verständlich sein: sofort erkennbar, was sie zeigt und was man tun kann.
- **Sekundär:** Ich selbst — als tatsächlich nutzbare Checkliste beim Abarbeiten der Käufe.

## 5. Persönlichkeit

Ruhig, präzise, hochwertig, leise selbstbewusst. Cineastisch-dunkel, aber warm genug,
um persönlich zu bleiben (es ist eine private Liste, kein Konzernauftritt).
Keine Verspieltheit, keine Emojis im Interface — die einzige Prise Persönlichkeit
kommt aus den Ich-Texten („Das hab ich mir vorgenommen", „Schon 12 von 209 erledigt").

## 6. Farbpalette

Dunkel, cineastisch, ein starker Akzent. Bewusst wärmer als das kühle Azur der letzten
Iteration — die Seite soll „Abendlicht am Schreibtisch" ausstrahlen, nicht „Dashboard".

| Rolle                  | Hex        | Einsatz                                          |
|------------------------|------------|--------------------------------------------------|
| Hintergrund tief       | `#0c0b09`  | Seitengrund (warmes Fast-Schwarz)                |
| Fläche                 | `#151310`  | Karten, Panels                                   |
| Fläche erhöht          | `#1d1a15`  | Hover-Flächen, Chips, Thumbnails                 |
| Hairline               | `#ffffff12`| Rahmen, Trennlinien (Weiß mit 7 % Alpha)         |
| Text                   | `#ece7de`  | Primärtext (warmes Off-White)                    |
| Text gedämpft          | `#948d80`  | Sekundärtext, Notizen                            |
| **Akzent**             | `#e8a33d`  | Amber/Messing — Summen, aktive Zustände, Fortschritt |
| Akzent dunkel          | `#b97f24`  | Hover-Abstufung des Akzents                      |
| Erfolg (abgehakt)      | `#79c99e`  | Check-Zustände, Fortschrittsbalken „erledigt"    |
| Info (Alternativen)    | `#8fa8d6`  | Gruppen vom Typ „noch nicht entschieden"         |

Regel: Amber ist der einzige laute Ton. Grün nur für Abhak-Zustände, Blau nur für
Alternativen-Gruppen. Nie mehr als ein Akzent pro Blickfeld.

## 7. Typografie

Alle Schriften via Google Fonts, mit Systemfallbacks:

- **Display / Headlines:** `Fraunces` (Serif mit Charakter, Optical Sizing, leicht warm) —
  Gewichte 500–600, enge Zeilenhöhe. Gibt der dunklen Seite das „teure" Editorial-Gefühl
  und unterscheidet sie von der üblichen Grotesk-auf-Schwarz-Ästhetik.
- **Interface / Fließtext:** `Inter` — 400/500/600, 15 px Basis, Zeilenhöhe 1.5.
- **Zahlen / Preise / Labels:** `JetBrains Mono` — 400/500, Tabellenziffern für Preise,
  gesperrte Uppercase-Micro-Labels (10–11 px, letter-spacing 0.14–0.18 em).

## 8. Wortmarke / Logo-Richtung

Reine Typo-Marke: `NOCH ZU HOLEN` in Fraunces 600, gesperrt (letter-spacing ~0.08 em),
davor ein kleines Quadrat in Amber (8×8 px, um 45° gedreht) als einziges Bildzeichen —
eine abstrahierte „Checkbox auf der Spitze". Das Zeichen taucht konsequent wieder auf:
als Favicon, als Bullet vor Sektions-Labels, als Abhak-Animation.

## 9. Beschreibung der Anwendung

Eine One-Page-Webanwendung (eine einzige HTML-Datei, kein Backend):

- **Datenbasis:** die bestehende Wunschliste — 209 Einträge in 9 Kategorien
  (Quelle: `Downloads/wunschliste.html`, `items`-Array bleibt die einzige Datenquelle).
- **Kernfunktion Checkliste:** Jeder Eintrag ist abhakbar. Der Haken wird in
  `localStorage` gespeichert und überlebt Neuladen — das ist hier erstmals sinnvoll,
  weil die Seite als echte lokale Datei lebt, nicht als flüchtiges Artefakt.
- **Fortschritt:** Kopfbereich mit Fortschrittsring/-balken („12 von 209 · 480 € von 31.685 €"),
  Fortschritt je Kategorie in den Sektionsköpfen.
- **Erhalten bleibt:** Suche, Kategorie-Tabs, Gruppen (Hauptprodukt + Zubehör,
  Alternativen, generisch), „Große Träume"-Projektansicht, Produktbilder mit Lightbox
  (`ITEM_IMAGES`-Map aus der bisherigen Version übernehmen).
- **Abgehakte Einträge** wandern optisch nach hinten (gedimmt, durchgestrichen, grüner Haken),
  bleiben aber sichtbar — die Liste erzählt auch, was schon geschafft ist.

## 10. Kern-Nutzen (für Sektionen / Feature-Momente)

1. Alles an einem Ort — 209 Wünsche, 9 Kategorien, eine Seite.
2. Abhaken mit Gedächtnis — der Fortschritt bleibt gespeichert.
3. Prioritäten auf einen Blick — Muss / Nice-to-have / Großer Traum.
4. Echte Produktbilder — ansehen statt nur lesen.
5. Große Träume als Projekte — z. B. die komplette Zimmer-Umgestaltung mit Bereichen.
6. Sofort findbar — Suche über Titel, Notizen, Marken, Gruppen.
7. Ehrliche Summen — was kostet der Rest, was ist schon erledigt.

## 11. Visuelle Stimmung

- **Licht:** ein warmer Lichtkegel von oben rechts (radialer Amber-Glow, 5–8 % Alpha)
  auf tiefem warmem Schwarz — Schreibtischlampe am Abend.
- **Material:** feines Filmkorn (SVG-Noise, ~3 % Opazität), Hairlines statt Kanten,
  weiche große Schatten unter erhöhten Flächen.
- **Bewegung:** langsam und wenige — Zahlen zählen beim Laden hoch, Karten treten beim
  Scrollen sanft ein (Reveal), der Fortschrittsring füllt sich animiert, Abhaken löst
  eine kleine, präzise Haken-Animation aus. Alles respektiert `prefers-reduced-motion`.
- **Kamera-Gefühl:** Der Hero wirkt wie eine ruhige Titel-Einstellung: große Serif-Zeile,
  viel Negativraum, darunter erst die Zahlen. Kein Parallax-Spektakel.

## 12. Ziel der Seite

1. In den ersten fünf Sekunden beeindrucken (Eltern-Test: „Das sieht ja aus wie gekauft").
2. In den nächsten zehn Sekunden verständlich sein: Das ist eine Kaufliste, man kann
   abhaken, der Fortschritt bleibt.
3. Danach tatsächlich benutzt werden — als mein echtes Abarbeitungs-Werkzeug.

## 13. Sektionsstruktur (Scroll-Reihenfolge)

1. **Hero** — Wortmarke, große Serif-Headline, Slogan, Fortschrittsring mit Kernzahlen.
2. **Ledger-Leiste** — Einträge gesamt · offen · erledigt · Restsumme (animierte Zähler).
3. **Kontroll-Leiste (sticky)** — Suche, „Alle Gruppen aufklappen", „Große Träume", Tabs.
4. **Kategorien-Sektionen** — je Kategorie: Kopf mit Mini-Fortschritt + Summe, darunter
   Karten und Gruppen (Bild links, Inhalt rechts, Haken-Control prominent).
5. **Große Träume** — Projektansicht (Zimmer-Umgestaltung → Bereiche), amber gerahmt.
6. **Footer** — eine Zeile Ich-Text + dezenter Hinweis „gebaut mit Claude Code" als
   Pointe für die Demo.

## 14. Hero-Hintergrund (optional, statt Video)

Ursprünglich war hier ein Higgsfield-Videobrief vorgesehen — für dieses Projekt ist ein
generiertes Video unnötig (Datei bleibt selbstständig und offline-fähig). Stattdessen,
falls ein Hero-Visual gewünscht: eine rein per CSS/SVG erzeugte Szene — warmer radialer
Lichtkegel, darunter eine flache Tisch-Silhouette aus zwei Verläufen, feines Korn darüber.
Keine Stockfotos, keine externen Medien im Hero.

---

### Nächste Schritte

- [x] `website/index.html` bauen (Struktur + Design nach diesem Kit)
- [x] Daten (`items` + `ITEM_IMAGES`) aus `Downloads/wunschliste.html` übernehmen
- [x] Abhak-Logik + `localStorage` + Fortschrittsanzeigen
- [x] Ausbau: lokale Bilder, Filter, Undo, Export/Import, Lightbox-Galerie,
      Druckansicht, Shortcuts, README + git
- [ ] Eltern-Test
