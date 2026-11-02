# ✈️ Gate Code

Ein Quiz rund um die Dreibuchstabencodes (IATA) der größten Flughäfen der Welt. Wie schnell erkennst du, dass **HND** Tokio Haneda ist und **SZX** Shenzhen?

**Jetzt spielen:** https://fstops.github.io/

---

## Spielprinzip

Eine Runde besteht aus **10 Flügen**. Pro Flug hast du **10 Sekunden**.

| Modus | Aufgabe |
| --- | --- |
| **Code erraten** | Du siehst einen Flughafen (z. B. „Tokio Haneda“) und tippst den Code auf der Abflugtafel. |
| **Stadt erraten** | Du siehst einen Code und wählst aus vier Antworten den passenden Flughafen. |

### Punkte

- Bis zu **100 Punkte pro Flug**, also **1000 pro Runde**.
- Die **erste Sekunde ist gratis**: Wer in ihr richtig antwortet, bekommt die vollen 100 Punkte.
- Danach sinkt der Wert gleichmäßig bis auf 0 nach 10 Sekunden.
- **Jeder Fehlversuch und jeder Tipp kostet ein Drittel** der erreichbaren Punkte.
- Läuft die Zeit ab, wird die Lösung gezeigt und es gibt 0 Punkte.

### Bestenliste

Nach der Runde trägst du deinen Namen ein. Der Reiter **Bestenliste** zeigt die zehn besten Runden mit Modus und Datum.

> Die Bestenliste wird im Browser des jeweiligen Geräts gespeichert (`localStorage`). Sie ist also nicht für alle Spieler gemeinsam sichtbar.

---

## Als App auf dem Handy

Gate Code ist eine Progressive Web App und läuft nach dem ersten Laden auch offline.

**Android (Chrome):**
1. https://fstops.github.io/ öffnen.
2. Menü (drei Punkte) → **Zum Startbildschirm hinzufügen** oder **App installieren**.

**iPhone (Safari):**
1. Seite öffnen, auf **Teilen** tippen.
2. **Zum Home-Bildschirm** wählen.

Eine APK lässt sich bei Bedarf mit [PWABuilder](https://www.pwabuilder.com) aus der Seitenadresse erzeugen.

---

## Projektstruktur

```
index.html            Spiel (Oberfläche, Logik, Punkte, Bestenliste)
airports.js           Liste der 100 Flughäfen
manifest.webmanifest  App-Daten für die Installation
sw.js                 Service Worker (Offline-Betrieb)
icon.svg, icon-*.png  App-Icons
```

Es gibt keine Abhängigkeiten und keinen Build-Schritt. Alles ist reines HTML, CSS und JavaScript.

---

## Flughäfen ergänzen

Jede Zeile in `airports.js` hat das Format `CODE|Name|Land`:

```
HND|Tokio Haneda|Japan
```

Neue Zeile anhängen, speichern, fertig. Pro Runde werden zehn Flughäfen zufällig gezogen. Die Codes sollten immer genau drei Großbuchstaben haben.

**Zur Auswahl:** Die ersten 20 Einträge folgen dem ACI-Ranking der meistfrequentierten Flughäfen 2025. Die übrigen 80 sind eine Auswahl großer Flughäfen aus allen Regionen und entsprechen nicht exakt den Plätzen 21 bis 100.

---

## Veröffentlichen und Aktualisieren

Das Projekt läuft über **GitHub Pages**:

1. Repository öffnen → **Settings → Pages**.
2. Bei *Source* **Deploy from a branch** wählen, Branch `main`, Ordner `/ (root)`.
3. Nach ein bis zwei Minuten ist die Seite online.

**Wichtig bei jeder Änderung:** In `sw.js` die Versionsnummer erhöhen (zum Beispiel `gatecode-v3` → `gatecode-v4`). Sonst zeigen installierte Apps weiter die alte Version aus dem Offline-Speicher.

---

## Ideen für später

- Gemeinsame Bestenliste für alle Spieler (benötigt einen kleinen Server)
- Tägliches Rätsel mit festem Flughafen für alle
- Weitere Modi, z. B. Länderquiz oder Zahlencode (A = 1, B = 2 …)

---
