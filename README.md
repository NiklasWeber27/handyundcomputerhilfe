# Handy- & Computerhilfe Niklas Weber — Website

Statische Ein-Seiten-Website (reines HTML/CSS/JS, kein Build-Prozess nötig).

## Ordnerinhalt

| Datei | Zweck |
|---|---|
| `index.html` | Die komplette Website |
| `impressum.html` | Impressum (gesetzlich vorgeschrieben) |
| `datenschutz.html` | Datenschutzerklärung (gesetzlich vorgeschrieben) |
| `robots.txt` | Sagt Suchmaschinen, dass sie alles crawlen dürfen |
| `sitemap.xml` | Liste der Seiten für Suchmaschinen (aktuell nur die eine Seite) |
| `site.webmanifest` | Icon/Name-Infos, falls jemand die Seite "installiert" (PWA-Metadaten) |
| `favicon.ico`, `favicon-16x16.png`, `favicon-32x32.png`, `favicon-48x48.png` | Browser-Tab-Icons |
| `apple-touch-icon.png` | Icon, wenn jemand die Seite auf dem iPhone-Homescreen speichert |
| `icon-192.png`, `icon-512.png` | Icons für Android/PWA |
| `og-image.png` | Vorschaubild, wenn der Link auf WhatsApp/Facebook/LinkedIn geteilt wird |
| `.nojekyll` | Verhindert, dass GitHub Pages die Seite fälschlich durch Jekyll verarbeitet |

## Vor dem Veröffentlichen: Impressum vervollständigen

In `impressum.html` steht eine Stelle, die ich **nicht erfinden konnte** und die du
noch selbst ergänzen musst:

- **Zuständige Gewerbebehörde** und **WKO-Fachgruppe** (in der Regel Magistrat
  Innsbruck bzw. deine Bezirkshauptmannschaft — steht auf deinem Gewerbeschein
  bzw. deiner WKO-Mitgliedsbestätigung)

Diese Stelle ist in der Datei gelb markiert und mit "bitte ergänzen" beschriftet.

Die GISA-Zahl (deine Gewerberegister-Nummer) ist rechtlich **keine Pflichtangabe**
nach § 5 ECG oder § 63 GewO — auch das offizielle WKO-Musterimpressum führt sie nicht
als Pflichtfeld. Sie steht deshalb nur als optionale Ergänzung drin; du kannst sie
weglassen oder später über das [GISA-Auskunftssystem](https://www.gisa.gv.at) ergänzen.

## Deine Domain: handyundcomputerhilfe.at

Die Platzhalter sind bereits überall durch `https://handyundcomputerhilfe.at` ersetzt
(in `index.html`, `robots.txt` und `sitemap.xml`). Du musst nur noch die Domain bei
GitHub Pages hinterlegen und beim Domain-Anbieter die DNS-Einträge setzen.

## Veröffentlichen auf GitHub Pages

1. Neues Repository auf GitHub anlegen (z. B. `handy-computerhilfe-niklas-weber`).
   Für eine „nackte" Domain ohne Unterordner: Repo-Name `DEINUSERNAME.github.io`.
2. Alle Dateien aus diesem Ordner in das Repository hochladen (z. B. per Drag & Drop
   im Browser auf GitHub, oder mit `git add . && git commit -m "Website" && git push`).
3. Im Repository: **Settings → Pages**.
4. Bei **Source** „Deploy from a branch" wählen, Branch `main`, Ordner `/ (root)`.
5. Speichern — nach ein bis zwei Minuten ist die Seite unter der angezeigten
   `github.io`-URL live.
6. Eigene Domain `handyundcomputerhilfe.at` verbinden:
   - Die Datei `CNAME` mit dem Inhalt `handyundcomputerhilfe.at` liegt bereits in diesem
     Ordner — die brauchst du nur mit hochzuladen, GitHub Pages erkennt sie automatisch.
   - Zur Kontrolle: unter **Settings → Pages → Custom domain** sollte danach
     `handyundcomputerhilfe.at` stehen.
   - Bei deinem Domain-Anbieter (dort, wo du `handyundcomputerhilfe.at` registriert hast)
     folgende DNS-Einträge setzen:
     - Vier **A-Records** auf die Root-Domain (`@`), zeigend auf:
       `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
     - Optional ein **CNAME-Record** für `www` auf `DEINUSERNAME.github.io`
   - Das kann bis zu 24 Stunden dauern, meistens geht's aber innerhalb weniger Minuten.
   - Danach in **Settings → Pages** "Enforce HTTPS" aktivieren, sobald die Option
     anwählbar ist (braucht auch etwas Zeit nach der DNS-Umstellung).

## Danach prüfen

- Google Search Console: Property anlegen, `sitemap.xml` einreichen.
- Link-Vorschau testen: URL beim [Facebook Sharing Debugger](https://developers.facebook.com/tools/debug/)
  oder [Twitter Card Validator](https://cards-dev.twitter.com/validator) eingeben, ob
  `og-image.png` korrekt angezeigt wird.
- Kontaktformular: aktuell ein `mailto:`-Link (öffnet das Mail-Programm des Besuchers).
  Für ein echtes serverseitiges Formular später ggf. einen Dienst wie Formspree oder
  Web3Forms anbinden.
