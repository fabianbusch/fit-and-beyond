# 006 – Zeitübungen automatisch abhaken

**Status:** Abgestimmt (Freigabe Fabian, 2026-10-15)
**Erstellt:** 2026-10-11 · **Überarbeitet:** 2026-10-12
**Bezug:** Handzettel „Übungszeit durch Übung automatisch Satzcheck (Planke …)“
**Hängt zusammen mit:** 001 (Ist-Wert, Anstrengung), 002 (Los-Knopf), 003 (Töne, Start-Countdown), 009 (Steigerung)

## Problem

Beim Unterarmstütz startet man den Halte-Timer, hält, steht auf und muss dann noch den Satz von Hand abhaken. Erst danach startet die Pause. Das ist ein überflüssiger Schritt mitten in der Erschöpfung, und es kostet Pausenzeit.

## Ziel

Bei Übungen auf Zeit erledigt die App den Satz selbst, sobald die Haltezeit abgelaufen ist, und geht direkt in den nächsten Schritt über. Gestartet wird wie überall mit „Los“.

## Scope

**Drin:**
- Start über „Los“ mit direkt anschließendem 3-2-1 aus 003
- Automatisches Abhaken bei Ablauf der Haltezeit
- Zeitübungen pro Seite mit eigenem „Los“ je Seite
- Vorzeitiges Beenden mit Übernahme der gehaltenen Zeit
- Dehnungen im Abschluss mit Timer, Seitenwechsel-Signal und automatischem Abhaken

**Nicht drin:**
- Automatisches Abhaken bei Wiederholungsübungen. Das kann die App nicht wissen.
- Automatisches Steigern der Haltezeit. Das gehört in das eigene Feature [009 – Steigerung](009-steigerung.md).

## Fachliche Regeln

### Start

1. **Betroffene Übungen:** alle Übungen, deren Dosierung eine Zeit ist. Im Plan derzeit nur der Unterarmstütz, künftig auch zeitbasierte Burner (005) und Alternativen (007), z. B. Seitstütz.
2. **Start über „Los“:** Der Pflicht-Knopf „Los“ aus 002 startet die Übung. Einen eigenen Knopf „Halten“ gibt es nicht mehr.
3. **Kein Vorlauf:** Nach „Los“ beginnt **unmittelbar** der Start-Countdown 3-2-1 mit „In Position“ (003, Regel 9). Es gibt keine zusätzlichen stillen Sekunden davor. Mit dem Endsignal beginnt die Haltezeit, der Text wechselt zu „Halten“.
4. **Haltedauer:** Vorbelegt mit dem Ist-Wert desselben Satzes aus der letzten Einheit (001), sonst mit der oberen Grenze der Plan-Spanne (001, Regel 5), beim Unterarmstütz also 45 Sek. Vor „Los“ lässt sie sich in 5-Sek.-Schritten anpassen.

### Ende

5. **Ablauf der Haltezeit:** Das Ende kündigt sich mit 3-2-1 und Endsignal an, Text „Geschafft“ (003, Regel 10). Bei 0 wird der laufende Satz automatisch abgehakt. Ist-Wert ist die volle Haltezeit.
6. **Danach wie beim normalen Abhaken:** Es erscheint die Anstrengungsauswahl mit 5 Sek. Wartezeit (001, Regel 3), danach startet die Pause. Das Handy muss dafür nicht berührt werden.
7. **Vorzeitig beenden:** Wird während der Haltezeit „Stopp“ getippt, fragt die Leiste: „Gehaltene 24 Sek. werten?“ mit „Werten“ und „Verwerfen“.
   - **Werten:** Satz erledigt, Ist-Wert sind die gehaltenen Sekunden. Weiter wie in Regel 6.
   - **Verwerfen:** Satz bleibt offen und braucht ein neues „Los“ (002, Regel 10).
8. **Stopp im Start-Countdown:** Wird während des 3-2-1 „Stopp“ getippt, gilt das als „Abbrechen“ nach 002, Regel 10. Der Satz bleibt offen, nichts wird gewertet.

### Zeitübungen pro Seite

9. **Eigenes „Los“ pro Seite:** Läuft eine Zeitübung pro Seite, z. B. Seitstütz als Alternative, bekommt jede Seite ein eigenes „Los“, ein eigenes 3-2-1 und eine eigene Haltezeit:
   - links: „Los“ → 3-2-1 → halten → Ende, automatisch abgehakt
   - rechts: „Los“ → 3-2-1 → halten → Ende, automatisch abgehakt
10. **Zwischen den Seiten:** Nach der linken Seite erscheint die Anstrengungsauswahl, aber kein Pausentimer. Die Leiste bietet direkt „Los rechts“ an. Die Pause startet erst nach der rechten Seite (001, Regel 2; 002, Regel 3).
11. **Erfassung:** Ist-Wert, Anstrengung und Übungszeit werden pro Seite gespeichert (001, 002).

### Dehnungen im Abschluss

12. **Timer auch für Dehnungen:** Jede Dehnung im Abschluss, deren Dosierung eine Zeit ist, läuft mit Timer und hakt sich selbst ab. Heute sind das Hüftbeuger-Dehnung (30 Sek. pro Seite), Kindhaltung (60 Sek., Obergrenze der Spanne 45–60) und Brustdehnung im Türrahmen (30 Sek. pro Seite).
13. **Start:** Eine Dehnung startet mit „Los“, danach das 3-2-1 mit „In Position“, dann die Haltezeit, wie bei allen Zeitübungen (Regel 3). Damit gilt die Ausnahme „Abschluss ohne Los“ aus 002 nur noch für den Fall, dass eine Abschlussübung keine Zeitangabe hat.
14. **Seitenwechsel bei Dehnungen:** Bei Dehnungen pro Seite läuft der Seitenwechsel automatisch, ohne zweites „Los“:
    - Ende links mit 3-2-1 und Endsignal, Text „Seite wechseln“
    - 5 Sek. Wechselzeit, deren letzte 3 Sekunden mit 3-2-1 laufen
    - rechte Seite mit voller Haltezeit, Ende mit 3-2-1, Endsignal und „Geschafft“
15. **Bewusster Unterschied zu Regel 9:** Kraft-Zeitübungen pro Seite haben je Seite ein eigenes „Los“, weil dort Ist-Werte und Zeiten pro Seite erfasst werden. Dehnungen dienen der Entspannung, haben keine Erfassung (001) und laufen deshalb ohne zweiten Tap durch.
16. **Danach:** Nach einer Dehnung gibt es keine Anstrengungsauswahl, keinen Ist-Wert und keine Pause. Die Leiste bietet direkt „Los“ für die nächste Dehnung an.
17. **Stopp:** „Stopp“ während einer Dehnung beendet sie, die Dehnung bleibt offen. Sie lässt sich wie bisher auch von Hand abhaken.

### Zeiten

18. **Übungszeit:** Die Übungszeit nach 002 beginnt mit „Los“ und schließt das 3-2-1 ein (003, Regel 11). Sie endet mit dem automatischen oder manuellen Abhaken.

## Akzeptanzkriterien

- [ ] Nach „Los“ beim Unterarmstütz startet sofort das hörbare 3-2-1, ohne stille Wartezeit davor. Danach beginnt die Haltezeit.
- [ ] Nach Ablauf der Haltezeit ist der Satz abgehakt, und nach der Anstrengungsauswahl läuft die Pause, ohne dass das Handy berührt wurde.
- [ ] Ein vorzeitiger Stopp mit „Werten“ speichert die tatsächlich gehaltene Zeit.
- [ ] Ein vorzeitiger Stopp mit „Verwerfen“ lässt den Satz offen, er braucht ein neues „Los“.
- [ ] Ein Stopp während des 3-2-1 bricht ab, ohne etwas zu werten.
- [ ] Bei einer Zeitübung pro Seite braucht jede Seite ein eigenes „Los“ mit eigenem 3-2-1. Zwischen den Seiten startet keine Pause, nach der rechten Seite schon.
- [ ] Im Protokoll stehen bei Zeitübungen pro Seite getrennte Haltezeiten für links und rechts.
- [ ] Jede Dehnung im Abschluss startet mit „Los“ und 3-2-1, läuft mit Timer und hakt sich am Ende selbst ab.
- [ ] Bei Dehnungen pro Seite kommt nach der ersten Seite ein hörbares Seitenwechsel-Signal, die zweite Seite startet nach 5 Sek. Wechselzeit von selbst.

## Offene Fragen

Keine.

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| 2026-10-12 | Start über „Los“ mit unmittelbar folgendem 3-2-1, kein stiller Vorlauf, kein eigener Knopf „Halten“ | 3 Sekunden reichen, um in Position zu gehen. Einheitlich mit dem Pflicht-„Los“ aus 002 und den Tönen aus 003. |
| 2026-10-12 | Zeitübungen pro Seite: jede Seite mit eigenem „Los“, eigenem 3-2-1 und eigener Haltezeit | Konsistent zu „Los“ pro Seite in 002 und getrennter Erfassung in 001 |
| 2026-10-12 | Dehnungen im Abschluss laufen mit Timer und haken sich selbst ab, bei Dehnungen pro Seite mit automatischem Seitenwechsel-Signal | Wunsch Fabian: Wo „30 Sekunden halten“ steht, soll auch ein Timer laufen |
| 2026-10-12 | Automatisches Steigern der Haltezeit nicht in 006, sondern im eigenen Feature 009 | Steigerung betrifft Wiederholungen, Gewicht und Haltezeit gleichermaßen und soll an einer Stelle geregelt werden |
