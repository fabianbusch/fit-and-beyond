# Fachkonzept – Ist-Stand

**Stand:** 2026-10-11 · Version 0.4 (erste veröffentlichte Fassung nach vier Iterationen im Chat)

Dieses Dokument beschreibt, was die App fachlich heute kann. Es wird nach jedem umgesetzten Feature aktualisiert.

## Zielbild

Fabian steigt nach längerer Sportpause wieder ins Training ein. Vorher hat er Bodyweight trainiert. Ziele: Muskeln aufbauen, fitter werden, sich gut fühlen. Die App begleitet eine Einheit zu Hause, Schritt für Schritt, am Handy.

**Vorhandenes Equipment:** eine verstellbare Kurzhantel mit Schraubverschlüssen, ein Hip-Band aus Stoff, eine Matte. Für eine Dehnung zusätzlich ein Türrahmen, für das Rudern optional ein Stuhl.

## Rahmenbedingungen

### Datenhaltung (entschieden 2026-10-11)

Persönliche Daten wie Fortschritt, Ist-Leistungen, Zeiten und Einstellungen werden **lokal im Browser** gespeichert, bis es ein echtes Backend gibt.

Das hat Folgen, die jedes Feature berücksichtigen muss:
- Die Daten gibt es nur auf dem Gerät und in dem Browser, in dem trainiert wird. Handy und Laptop teilen nichts.
- Beim Leeren der Browserdaten oder im privaten Modus gehen sie verloren. Die App muss dann trotzdem normal funktionieren, nur ohne Verlauf.
- Die Daten hängen an der Adresse, unter der die App läuft. Wechselt die Adresse, etwa vom Claude-Artefakt zu einer eigenen Seite, startet der Verlauf leer, sofern es keinen Export und Import gibt.
- Ein späteres Backend soll die vorhandenen Daten übernehmen können. Deshalb werden sie von Anfang an strukturiert und mit Datum gespeichert.

## Glossar

| Begriff | Bedeutung |
|---|---|
| **Einheit** | Ein komplettes Training von Aufwärmen bis Abschluss |
| **Block** | Gruppe von Übungen, die zusammen trainiert werden (Aufwärmen, Block A–C, Abschluss) |
| **Übung** | Eine einzelne Bewegung, z. B. Goblet Squat |
| **Wiederholung (Wdh.)** | Einmal die Bewegung ausführen |
| **Satz** | Eine Übung einmal am Stück mit der vorgegebenen Anzahl Wiederholungen oder Haltezeit |
| **Runde** | Innerhalb eines Blocks einmal jede Übung für einen Satz durchlaufen |
| **Zirkel** | Trainingsform, bei der ein Block in Runden statt Satz für Satz pro Übung absolviert wird |
| **Pause** | Erholung nach einem Satz, Standard 60–90 Sek. |
| **Reserve (RIR)** | Wiederholungen, die man am Satzende noch schaffen würde. Ziel im Wiedereinstieg: 2–3 |

**Merksatz:** 3 Runden mit je 1 Satz pro Übung ergeben 3 Sätze pro Übung.

## Trainingsplan

Dauer ca. 35–40 Minuten.

| Block | Form | Übungen | Dosierung |
|---|---|---|---|
| Aufwärmen | einmal durch, ohne Pause | Armkreisen · Kniebeugen ohne Gewicht · Hüftbrücke · Inchworm | 10/10 · 10 · 10 · 5 Wdh. |
| A · Beine & Drücken | Zirkel, 3 Runden | Goblet Squat · Liegestütze | 10–12 · 6–12 Wdh. |
| B · Rücken & Po | Zirkel, 3 Runden | Einarmiges Rudern · Glute Bridge mit Band | 10 pro Seite · 15 Wdh. mit 2 Sek. Halten |
| C · Schultern & Rumpf | Zirkel, 3 Runden | Einarmiges Schulterdrücken · Seitliche Band-Walks · Unterarmstütz | 8–10 pro Seite · 10 Schritte pro Richtung · 30–45 Sek. |
| Abschluss | einmal durch | Hüftbeuger-Dehnung · Kindhaltung · Brustdehnung im Türrahmen | 30 Sek. pro Seite · 45–60 Sek. · 30 Sek. pro Seite |

### Angaben pro Übung

Jede Übung zeigt:
- Name und Dosierung
- Hilfsmittel, oder „keine“
- Muskeln, getrennt nach Hauptmuskeln und Hilfsmuskeln
- Ablauf in 3–4 Schritten
- Optional einen Technik-Tipp

### Gewichtsempfehlung (nur im Chat, noch nicht in der App)

Das Gewicht so wählen, dass 2–3 Wiederholungen Reserve bleiben. Grobe Startwerte: Goblet Squat 8–12 kg, Rudern 6–10 kg, Schulterdrücken 4–7 kg. Steigern, wenn in allen 3 Runden das obere Ende der Wiederholungen locker klappt.

## Funktionen

### F1 · Vorbereitung
Ein Hinweiskasten vor dem Start: Sternmuttern festziehen, Band, Matte und Wasser bereitlegen, barfuß oder in flachen Schuhen trainieren.

### F2 · Satz-Tracking
- In Zirkel-Blöcken hat jede Übung die Felder „Satz 1“, „Satz 2“ und „Satz 3“.
- Aufwärm- und Abschlussübungen haben ein Feld „Erledigt“.
- Ein Feld lässt sich durch erneutes Antippen wieder abwählen.
- Eine Übung gilt als erledigt, wenn alle ihre Sätze erledigt sind. Sie wird dann grün markiert.

### F3 · Rundenanzeige
- Jeder Zirkel-Block zeigt „Runde N / 3“. N ist die niedrigste Runde, in der noch ein Satz offen ist.
- Das Abzeichen ist hervorgehoben, wenn der nächste offene Satz in diesem Block liegt, sonst gedämpft.
- Sind alle Sätze des Blocks erledigt, steht dort „Erledigt“.

### F4 · Ablaufreihenfolge
Die vorgesehene Reihenfolge ist rundenweise: Block für Block, darin Runde für Runde, darin Übung für Übung. Beispiel Block A: Goblet Squat Satz 1 → Liegestütze Satz 1 → Goblet Squat Satz 2 → …

Der „nächste Schritt“ ist immer der erste offene Satz in dieser Reihenfolge, auch wenn außer der Reihe abgehakt wurde.

### F5 · Timer-Leiste
Fest am unteren Bildschirmrand.
- **Ruhezustand:** zeigt „Als Nächstes: Übung“ mit Ort, z. B. „Block A · Runde 2 von 3 · Satz 2“. Startknöpfe für 60 und 90 Sek. Pause.
- **Automatische Pause:** Nach dem Abhaken eines Satzes in einem Zirkel-Block startet automatisch eine Pause von 60 Sek. Das gilt nicht für Aufwärmen und Abschluss und nicht, wenn danach nichts mehr offen ist.
- **Während der Pause:** Countdown, Fortschrittsbalken, Hinweis „danach Übung“ mit Ort, Knöpfe „+15“ und „Stopp“.
- **Halte-Timer:** Der Unterarmstütz hat einen Knopf „Halten 40 s“, der einen Arbeits-Countdown startet. Der Satz wird danach von Hand abgehakt.
- **Ende eines Countdowns:** dreifacher Piepton und Vibration, soweit das Gerät es erlaubt.
- Der Bildschirm bleibt während eines Timers wach, soweit das Gerät es erlaubt.

### F6 · Fortschritt
- Fortschrittsbalken und Zähler „erledigte / alle Sätze“ im Kopf, aktuell 28 Einträge: 4 Aufwärmübungen, 21 Zirkel-Sätze, 3 Dehnungen.
- Der Fortschritt wird nur im Browser des Geräts gespeichert, geräteübergreifend gibt es ihn nicht.
- „Fortschritt zurücksetzen“ verlangt eine Bestätigung durch zweites Antippen innerhalb von 3 Sek.

### F7 · Darstellung
- Optimiert fürs Handy, funktioniert auch am Desktop
- Helles und dunkles Design, je nach Systemeinstellung
- Sprache: Deutsch

## Bekannte Lücken

Aus dem bisherigen Chat, noch nicht spezifiziert:

- Pausendauer ist fest 60 Sek., der Plan nennt 60–90 Sek.
- Gewichte werden weder angezeigt noch erfasst.
- Es gibt keinen Verlauf über mehrere Einheiten und keine Steigerungslogik.
- Es gibt keinen 4-Wochen-Plan und keine Cardio-Tage.
- Weiteres Feedback von Fabian steht noch aus.
