# 006 – Zeitübungen automatisch abhaken

**Status:** Entwurf
**Erstellt:** 2026-10-11 · **Überarbeitet:** 2026-10-12
**Bezug:** Handzettel „Übungszeit durch Übung automatisch Satzcheck (Planke …)“
**Hängt zusammen mit:** 001 (Ist-Wert, Anstrengung), 002 (Los-Knopf), 003 (Töne, Start-Countdown)

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

**Nicht drin:**
- Automatisches Abhaken bei Wiederholungsübungen. Das kann die App nicht wissen.
- Dehnungen im Abschluss. Siehe offene Frage 1.

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

### Zeiten

12. **Übungszeit:** Die Übungszeit nach 002 beginnt mit „Los“ und schließt das 3-2-1 ein (003, Regel 11). Sie endet mit dem automatischen oder manuellen Abhaken.

## Akzeptanzkriterien

- [ ] Nach „Los“ beim Unterarmstütz startet sofort das hörbare 3-2-1, ohne stille Wartezeit davor. Danach beginnt die Haltezeit.
- [ ] Nach Ablauf der Haltezeit ist der Satz abgehakt, und nach der Anstrengungsauswahl läuft die Pause, ohne dass das Handy berührt wurde.
- [ ] Ein vorzeitiger Stopp mit „Werten“ speichert die tatsächlich gehaltene Zeit.
- [ ] Ein vorzeitiger Stopp mit „Verwerfen“ lässt den Satz offen, er braucht ein neues „Los“.
- [ ] Ein Stopp während des 3-2-1 bricht ab, ohne etwas zu werten.
- [ ] Bei einer Zeitübung pro Seite braucht jede Seite ein eigenes „Los“ mit eigenem 3-2-1. Zwischen den Seiten startet keine Pause, nach der rechten Seite schon.
- [ ] Im Protokoll stehen bei Zeitübungen pro Seite getrennte Haltezeiten für links und rechts.

## Offene Fragen

1. **Dehnungen:** Sollen die Dehnungen im Abschluss (30 Sek. pro Seite) auch mit Timer laufen und sich selbst abhaken? Nach 002 brauchen sie bisher kein „Los“.
2. **Haltedauer steigern:** Soll die App die Haltezeit von selbst erhöhen, wenn das Ziel erreicht wurde? Das gehört eigentlich zum späteren Feature „Steigerungsvorschläge“.

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| 2026-10-12 | Start über „Los“ mit unmittelbar folgendem 3-2-1, kein stiller Vorlauf, kein eigener Knopf „Halten“ | 3 Sekunden reichen, um in Position zu gehen. Einheitlich mit dem Pflicht-„Los“ aus 002 und den Tönen aus 003. |
| 2026-10-12 | Zeitübungen pro Seite: jede Seite mit eigenem „Los“, eigenem 3-2-1 und eigener Haltezeit | Konsistent zu „Los“ pro Seite in 002 und getrennter Erfassung in 001 |
