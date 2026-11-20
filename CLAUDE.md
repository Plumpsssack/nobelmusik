# nobelmusik

Website des Musikers Nobel. Astro (statisch), gehostet auf GitHub Pages mit eigener Domain.

## Befehle
- `npm install` – Abhängigkeiten
- `npm run dev` – lokaler Server (http://localhost:4321)
- `npm run build` – statischer Build nach `dist/`

## Aufbau
- `src/layouts/Base.astro` – gemeinsames Layout, `<ClientRouter />` für View Transitions
- `src/pages/index.astro` – Startseite: Vollbild-Foto, Logo auf der schrägen Säule, Profil-Links auf der rechten Säule, EP-Block oben
- `src/pages/impressum.astro`, `datenschutz.astro` – Pflichtseiten (Platzhalter in [ECKIGEN KLAMMERN] ausfüllen)
- `src/styles/global.css` – Farben (CSS-Variablen) und Schriften
- `public/images/` – hero.jpg (Foto, 2:3), logo.png, wall-strip.png (oberste Bildzeile, verlängert die Wand nach oben)
- `deploy-workflow.yml` – Deployment auf GitHub Pages bei Push auf `main`. TODO: nach `.github/workflows/deploy.yml` verschieben (konnte beim Anlegen nicht direkt dort gespeichert werden).

## Wichtig
- Logo und Säulen-Links sind in % der Bildfläche positioniert (`.stage`, 2:3). Bei einem neuen Foto mit anderem Ausschnitt müssen `left`/`top`/Rotation neu bestimmt werden.
- Die Bildfläche wird nie beschnitten; auf hohen Handys verlängert `.ext` die Wand nach oben.
- Schriften lokal über @fontsource (kein Google-Fonts-Request, DSGVO).
- Unterseiten mit Zoom-Übergang: gleiches `transition:name` auf beiden Seiten setzen.
- Versionen der GitHub Actions im Deploy-Workflow vor dem ersten Deploy auf aktuelle Releases prüfen.
