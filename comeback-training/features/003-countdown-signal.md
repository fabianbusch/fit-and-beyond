# 003 – Countdown-Signal am Ende von Pausen und Haltezeiten

**Status:** Entwurf
**Erstellt:** 2026-10-11
**Bezug:** Handzettel „Pause Ende → Signalton & Countdown“

## Problem

Heute kommt erst bei 0 Sekunden ein Piepton. Man ist dann nicht in Position und verliert Zeit, oder man schaut ständig aufs Handy, das auf dem Boden liegt.

## Ziel

Das Ende einer Pause oder Haltezeit kündigt sich hörbar und sichtbar an, sodass man ohne Blick aufs Display bereit ist.

## Scope

**Drin:**
- Vorwarnung in den letzten Sekunden einer Pause
- Gleiches Verhalten für den Halte-Timer (Unterarmstütz)
- Gut erkennbares Endsignal
- Große Countdown-Ziffern in den letzten Sekunden
- Ton ein- und ausschalten

**Nicht drin:**
- Sprachansagen (möglich als Folgefeature)
- Signale bei gesperrtem Bildschirm. Ein Browser kann das nicht zuverlässig, deshalb bleibt der Bildschirm wie heute während eines Timers wach.

## Fachliche Regeln

1. **Vorwarnung:** In den letzten 3 Sekunden ertönt pro Sekunde ein kurzer, heller Ton (3 – 2 – 1). Siehe offene Frage 1.
2. **Endsignal:** Bei 0 ertönt ein längerer, tieferer Ton, der sich klar von der Vorwarnung unterscheidet. Das Gerät vibriert, soweit es das unterstützt.
3. **Halbzeit bei langen Pausen:** Bei Pausen ab 60 Sek. ertönt bei noch 10 Sekunden ein einzelner Hinweiston. Siehe offene Frage 2.
4. **Visuell:** In den letzten 3 Sekunden wird die Restzeit in der Leiste groß und hervorgehoben angezeigt.
5. **Pause und Halten unterscheiden sich:** Am Ende einer Pause heißt es „Los“, am Ende einer Haltezeit „Geschafft“. Die Töne sind gleich, der Text unterscheidet sich.
6. **Ton aus:** Ein Schalter in der Leiste schaltet alle Töne stumm. Die Einstellung wird im Browser gemerkt. Vibration und Anzeige bleiben.
7. **„+15“ während der Vorwarnung:** Wer in den letzten 3 Sekunden „+15“ tippt, stoppt die Vorwarnung, und sie startet später neu.

## Akzeptanzkriterien

- [ ] Mit dem Handy auf dem Boden ist das Pausenende ohne Hinsehen klar zu hören, Vorwarnung und Endsignal sind unterscheidbar.
- [ ] Beim Unterarmstütz zählen die letzten 3 Sekunden hörbar herunter.
- [ ] Mit Ton aus bleibt es still, die großen Ziffern erscheinen trotzdem.
- [ ] Die Stummschaltung ist nach Neuladen noch aktiv.

## Offene Fragen

1. **Länge der Vorwarnung:** 3 Sekunden, oder lieber 5?
2. **10-Sekunden-Hinweis:** gewünscht, oder zu viel Gepiepe?
3. **Ton auch beim Start eines Halte-Timers?** Ein 3-2-1 vor dem Start, um in Position zu kommen, steht in 006. Soll es dort dieselben Töne nutzen?

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| | | |
