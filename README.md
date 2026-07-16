# KMSZ HLA-Simulator

Interaktive Präsentationsplattform zur Wissenschaftskommunikation rund um die Stammzellspende.

## Dateien
- `start.html` — Vortragenden-Ansicht: Session erzeugen, QR-Code, Live-Teilnehmerzähler, Link zur Ergebnisse-Ansicht.
- `index.html` — Publikums-Ansicht (Smartphone): HLA-Abgleich mit animiertem Scan, Ergebnis mit didaktischer Einordnung und Spender-CTA. Ziel des QR-Codes.
- `results.html` — Leinwand-/Beamer-Ansicht: Live-Auswertung in Echtzeit (Firestore `onSnapshot`), adaptive Kernaussage, Verteilungsdiagramm.
- `theme.css` — gemeinsames Designsystem (Farben, Typografie, Komponenten, Motion).
- `logo.png` — KMSZ-Logo (weiß, für dunkle Oberflächen).

## Design / Corporate Identity
Helles, offizielles Erscheinungsbild im KMSZ-Markenblau `#4FA3DB` (aus dem Logo).
Das Logo (`logo-blue.png`, aus dem Original recoloriert) ist auf jeder Seite prominent platziert.
Kein dunkler Hintergrund, kein Orange – Kontraste entstehen ausschließlich aus Abstufungen des Markenblaus.

Zusätzliche Assets: `logo-blue.png` (Markenblau, für helle Flächen), `logo.png` (weiß, für blaue Flächen).

## Wichtig vor dem Einsatz
Der Spender-CTA in `index.html` verlinkt auf `https://www.lifelolli.de` (Konstante `REGISTER_URL`).

## Deployment
Dateien in das Repository `tunakmz/kmsz-simulator` (Branch `main`, Root) übernehmen und committen.
GitHub Pages veröffentlicht automatisch unter `https://tunakmz.github.io/kmsz-simulator/`.
Firebase-Konfiguration und Firestore-Collection (`results`) bleiben unverändert.

## Was sich geändert hat
- Vollständiges, konsistentes Designsystem statt Inline-Styles (dunkle, ruhige Produktoberfläche, Inter, Motion).
- Ergebnis-Screen mit emotionaler/didaktischer Einordnung: „Treffer sind selten – deshalb zählt jede Registrierung."
- Echtzeit-Ergebnisse (`onSnapshot`, session-gefilterte Query) statt 3-Sekunden-Polling der gesamten Collection.
- Live-Teilnehmerzähler in der Vortragenden-Ansicht.
- QR groß, Session-ID gut lesbar, Link-Kopierfunktion.
- Lade-, Fehler- und Leerzustände; Reduced-Motion; Safe-Area/Mobile-Optimierung.
