# 003 – Countdown-Signale für Pausen und Haltezeiten

**Status:** Abgestimmt (Freigabe Fabian, 2026-10-15)
**Erstellt:** 2026-10-11 · **Überarbeitet:** 2026-10-12
**Bezug:** Handzettel „Pause Ende → Signalton & Countdown“
**Hängt zusammen mit:** 002 (Los-Knopf), 006 (Zeitübungen automatisch abhaken)

## Problem

Heute kommt erst bei 0 Sekunden ein Piepton. Man ist dann nicht in Position und verliert Zeit, oder man schaut ständig aufs Handy, das auf dem Boden liegt. Bei Halteübungen wie dem Unterarmstütz beginnt die Haltezeit sofort, obwohl man noch gar nicht in Position ist.

## Ziel

Pausenende, Start und Ende einer Haltezeit kündigen sich hörbar und sichtbar an, sodass man ohne Blick aufs Display bereit ist.

## Neue Begriffe

- **3-2-1:** drei kurze, helle Töne im Sekundentakt in den letzten 3 Sekunden eines Countdowns.
- **Endsignal:** ein längerer, tieferer Ton bei 0, klar unterscheidbar vom 3-2-1.
- **10-Sekunden-Hinweis:** ein einzelner kurzer Ton bei noch 10 Sekunden Pause.
- **Start-Countdown:** 3-2-1 nach „Los“ bei Halteübungen, bevor die Haltezeit beginnt.

## Scope

**Drin:**
- 3-2-1 und Endsignal am Ende jeder Pause
- 10-Sekunden-Hinweis bei Pausen ab 60 Sek.
- Start-Countdown 3-2-1 bei allen Halteübungen nach „Los“
- 3-2-1 und Endsignal am Ende jeder Haltezeit
- Große Countdown-Ziffern in den letzten Sekunden
- Ton ein- und ausschalten

**Nicht drin:**
- Sprachansagen (möglich als Folgefeature)
- Signale bei gesperrtem Bildschirm. Ein Browser kann das nicht zuverlässig, deshalb bleibt der Bildschirm wie heute während eines Timers wach.

## Fachliche Regeln

### Einheitliche Töne

1. **Ein Tonsatz für alles:** Pausenende, Start-Countdown und Haltezeit-Ende nutzen exakt dieselben Töne: 3-2-1 in den letzten 3 Sekunden, Endsignal bei 0. Sie unterscheiden sich nur im Text.
2. **3-2-1:** In den letzten 3 Sekunden ertönt pro Sekunde ein kurzer, heller Ton.
3. **Endsignal:** Bei 0 ertönt ein längerer, tieferer Ton. Das Gerät vibriert, soweit es das unterstützt.
4. **Visuell:** In den letzten 3 Sekunden wird die Restzeit in der Leiste groß und hervorgehoben angezeigt.

### Pause

5. **Pausenende:** Die Pause endet mit 3-2-1 und Endsignal. Der Text lautet dann „Los“ und weist auf den Los-Knopf aus 002 hin. Die Pause selbst endet erst mit „Los“, bis dahin zählt die Leiste die Überziehung (002, Regel 17).
6. **10-Sekunden-Hinweis:** Bei Pausen ab 60 Sek. ertönt bei noch 10 Sekunden ein einzelner kurzer Hinweiston, vor dem 3-2-1. Da die Standardpause fest 60 Sek. beträgt (002, Regel 16), greift er bei jeder Standardpause.
7. **„+15“ während des Countdowns:** Wer in den letzten 10 Sekunden „+15“ tippt, verschiebt das Ende. 10-Sekunden-Hinweis und 3-2-1 kommen dann zur neuen Endzeit erneut.
8. **Los vor Ablauf:** Wird „Los“ vor Ablauf der Pause gedrückt, endet sie sofort ohne weitere Töne.

### Halteübungen

9. **Start-Countdown:** Bei Halteübungen, heute dem Unterarmstütz und künftig allen zeitbasierten Übungen aus 005 und 007, übernimmt „Los“ den Start. Nach „Los“ läuft zuerst ein Start-Countdown 3-2-1 mit dem Text „In Position“. Mit dem Endsignal beginnt die Haltezeit, der Text wechselt zu „Halten“.
10. **Haltezeit-Ende:** Die Haltezeit endet mit 3-2-1 und Endsignal. Der Text lautet dann „Geschafft“. Was danach mit dem Satz passiert, legt 006 fest.
11. **Übungszeit:** Die Übungszeit nach 002 beginnt mit „Los“, also einschließlich des Start-Countdowns.

### Ton aus

12. **Stumm:** Ein Schalter in der Leiste schaltet alle Töne stumm. Die Einstellung wird im Browser gemerkt. Vibration und große Ziffern bleiben.

## Akzeptanzkriterien

- [ ] Mit dem Handy auf dem Boden ist das Pausenende ohne Hinsehen klar zu hören, das 3-2-1 und das Endsignal sind unterscheidbar.
- [ ] Bei einer 60-Sek.-Pause kommt bei 0:10 ein einzelner Hinweiston, danach das 3-2-1 und das Endsignal.
- [ ] Nach „Los“ beim Unterarmstütz läuft zuerst ein hörbares 3-2-1 mit „In Position“, erst danach beginnt die Haltezeit.
- [ ] Am Ende der Haltezeit kommen 3-2-1 und Endsignal mit dem Text „Geschafft“.
- [ ] Pause, Start-Countdown und Haltezeit-Ende klingen gleich, nur der Text unterscheidet sich.
- [ ] Mit Ton aus bleibt es still, die großen Ziffern erscheinen trotzdem.
- [ ] Die Stummschaltung ist nach Neuladen noch aktiv.

## Offene Fragen

Keine.

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| 2026-10-12 | Vorwarnung 3 Sek.: 3-2-1 mit kurzen, hellen Tönen, bei 0 ein längerer, tieferer Endton | 3 Sekunden reichen, um bereit zu sein. Endton klar vom Countdown unterscheidbar. |
| 2026-10-12 | 10-Sekunden-Hinweis bei Pausen ab 60 Sek. | „Gleich geht's weiter“, falls man in der Pause kurz abschaltet |
| 2026-10-12 | Start-Countdown 3-2-1 nach „Los“ bei allen Halteübungen, dann Haltezeit, am Ende erneut Endsignal | Besonders wichtig: Man muss erst in Position kommen, bevor die Haltezeit läuft |
