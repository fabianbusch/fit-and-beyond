# 008 – Bewegungsdarstellung der Übungen (menschliches Modell)

**Status:** Entwurf
**Erstellt:** 2026-10-12
**Bezug:** Sprachgespräch 2026-10-12, abgespalten von [004 – Muskelkarte](004-muskelkarte.md)

> **Hinweis zum Umfang:** Dies ist mit Abstand das größte und aufwendigste Feature. Es sprengt die bisherige „minimale Web-App“ und wird deshalb bewusst als eigenes Feature geführt. Es ist noch nicht abgestimmt, die zentralen Fragen unten sind offen.

## Problem

Gerade als Wiedereinsteiger weiß Fabian bei neuen Übungen nicht, wie sie aussehen. Die Textbeschreibungen sind teils unvorteilhaft oder missverständlich. Die farbige Muskelkarte (004) zeigt, **was** arbeitet, aber nicht, **wie** die Bewegung aussieht.

## Ziel

Pro Übung gibt es eine erkennbare, menschlich wirkende Darstellung der Bewegung. Daran erkennt man den Ablauf, die Körperhaltung (z. B. gerader Rücken) und die Stellung von Knien und Gelenken.

**Festlegung von Fabian:** Die Darstellung muss menschlich aussehen und die Bewegung klar zeigen. Ein abstraktes Strichmännchen ist ausdrücklich **nicht** gewollt.

## Scope

**Drin:**
- Eine Bewegungsdarstellung pro Übung, abspielbar direkt auf der Übungskarte
- Menschlich wirkende Figur oder Person
- Ergänzend zum Text-Ablauf und zur Muskelkarte aus 004, nicht als Ersatz

**Nicht drin (vorerst):**
- Echtzeit-Bewegungskorrektur per Kamera
- KI-Formcheck der eigenen Ausführung
- Abstrakte Strichfiguren

## Fachliche Regeln

Noch nicht festgelegt. Die Regeln ergeben sich erst aus den Antworten auf die offenen Fragen, vor allem aus Frage 1.

Bereits fest:

1. **Ergänzend:** Die Bewegungsdarstellung ergänzt den Text-Ablauf und die Muskelkarte (004). Beides bleibt erhalten.
2. **Menschlich:** Proportionen, Haltung und Gelenkstellung müssen so realistisch sein, dass man die Übung danach korrekt nachmachen kann.

## Akzeptanzkriterien

Vorläufig, werden nach Klärung von Frage 1 geschärft:

- [ ] Fabian kann eine Übung, die er noch nie gemacht hat, allein anhand der Darstellung in der richtigen Haltung ausführen.
- [ ] Rückenhaltung sowie Knie- und Ellbogenstellung sind in der Darstellung klar erkennbar.
- [ ] Die Darstellung wirkt menschlich, nicht wie ein Strichmännchen.
- [ ] Die App bleibt auf dem Handy flüssig bedienbar, auch wenn eine Darstellung geladen wird.

## Offene Fragen

1. **Umsetzungsweg** (die zentrale Frage):

   | | (a) 3D-Modell im Browser | (b) Videoclips oder animierte Bilder echter Menschen |
   |---|---|---|
   | **Was** | Gerigtes 3D-Modell mit Skelett, pro Übung eine Bewegungsanimation, abgespielt über eine 3D-Bibliothek im Browser (z. B. three.js oder model-viewer, Format glTF) | Kurze Clips, in denen eine Person die Übung sauber vormacht |
   | **Vorteile** | Interaktiv, drehbar, aus jedem Winkel betrachtbar, einheitlicher Stil über alle Übungen | Schnell verfügbar, meist klarer und realistischer, keine 3D-Erstellung nötig |
   | **Nachteile** | Aufwendig: Modell, Rig und eine Animation pro Übung nötig. Schlechte Animationen zeigen Fehlhaltungen. | Quelle, Lizenz und Hosting müssen geklärt werden. Größere Dateien. Nicht interaktiv. Uneinheitlicher Stil bei verschiedenen Quellen. |

2. **Herkunft der Assets:** Woher kommen Modell und Animationen beziehungsweise die Clips? Lizenz, Kosten, Qualität.
3. **Reihenfolge:** Welche Übungen zuerst? Vorschlag: die Hauptübungen der Blöcke A–C vor Aufwärmen und Abschluss.
4. **Auslieferung und Größe:** Die App wird über GitHub Pages ausgeliefert. Große Dateien wie 3D-Modelle oder Videos beeinflussen Ladezeit und Repo-Größe. Wo und wie werden sie gehostet?
5. **Offline und mobil:** Soll die Darstellung auf dem Handy auch bei schlechter Verbindung funktionieren?
6. **Verhältnis zu 004 und zum Text:** Wie sind Muskelkarte, Text-Ablauf und Bewegungsdarstellung auf der Übungskarte angeordnet? Fest ist nur, dass alle drei bleiben.

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| 2026-10-12 | Von 004 abgespalten, eigenes großes Feature | Die Muskelkarte (004) bleibt klein und schnell umsetzbar. Die menschlich wirkende Bewegungsdarstellung ist mit Abstand das aufwendigste Feature und braucht eine eigene, gründliche Klärung. |
| 2026-10-12 | Menschlich wirkende Darstellung, kein Strichmännchen | Vorgabe Fabian: Nur eine realistische Darstellung zeigt, wie die Übung wirklich aussieht. Textbeschreibungen und abstrakte Figuren reichen dafür nicht. |
