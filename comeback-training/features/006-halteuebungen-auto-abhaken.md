# 006 – Zeitübungen automatisch abhaken

**Status:** Entwurf
**Erstellt:** 2026-10-11
**Bezug:** Handzettel „Übungszeit durch Übung automatisch Satzcheck (Planke …)“

## Problem

Beim Unterarmstütz startet man den Halte-Timer, hält, steht auf und muss dann noch den Satz von Hand abhaken. Erst danach startet die Pause. Das ist ein überflüssiger Schritt mitten in der Erschöpfung, und es kostet Pausenzeit.

## Ziel

Bei Übungen auf Zeit erledigt die App den Satz selbst, sobald die Zeit abgelaufen ist, und startet direkt die Pause.

## Scope

**Drin:**
- Automatisches Abhaken bei Ablauf des Halte-Timers
- Direkter Übergang in die Pause
- Kurzer Vor-Countdown, um in Position zu kommen
- Vorzeitiges Beenden mit Übernahme der gehaltenen Zeit

**Nicht drin:**
- Automatisches Abhaken bei Wiederholungsübungen. Das kann die App nicht wissen.
- Dehnungen im Abschluss. Siehe offene Frage 2.

## Fachliche Regeln

1. **Betroffene Übungen:** alle Übungen, deren Dosierung eine Zeit ist. Im Plan derzeit nur der Unterarmstütz, künftig auch zeitbasierte Burner (005) und Alternativen (007), z. B. Seitstütz.
2. **Start:** Der Knopf „Halten“ startet zuerst einen Vor-Countdown von 5 Sek. mit dem Text „In Position“. Danach beginnt die eigentliche Haltezeit.
3. **Haltedauer:** Vorbelegt mit dem Ist-Wert der letzten Einheit (001), sonst 30 Sek. (untere Plan-Grenze). Vor dem Start lässt sie sich in 5-Sek.-Schritten anpassen.
4. **Ablauf:** Bei 0 wird der nächste offene Satz dieser Übung als erledigt markiert. Ist-Wert ist die volle Haltezeit. Danach startet die Pause wie bei manuellem Abhaken.
5. **Vorzeitig beenden:** Wird während der Haltezeit „Stopp“ getippt, fragt die Leiste: „Gehaltene 24 Sek. werten?“ mit „Werten“ und „Verwerfen“.
   - **Werten:** Satz erledigt, Ist-Wert sind die gehaltenen Sekunden, Pause startet.
   - **Verwerfen:** Satz bleibt offen, kein Timer.
6. **Übungen pro Seite:** Hat eine Zeitübung „pro Seite“, z. B. ein Seitstütz als Alternative, läuft die Zeit zweimal mit einem Wechselsignal und 5 Sek. Wechselzeit dazwischen.
7. **Signale:** Vor-Countdown und Ende nutzen die Töne aus 003.

## Akzeptanzkriterien

- [ ] Beim Unterarmstütz ist nach Ablauf der Haltezeit der Satz abgehakt und die Pause läuft, ohne dass das Handy berührt wurde.
- [ ] Der Vor-Countdown gibt genug Zeit, das Handy abzulegen und in Position zu gehen.
- [ ] Ein vorzeitiger Stopp mit „Werten“ speichert die tatsächlich gehaltene Zeit.
- [ ] Ein vorzeitiger Stopp mit „Verwerfen“ lässt den Satz offen.

## Offene Fragen

1. **Vor-Countdown:** 5 Sek. passend, oder lieber 10?
2. **Dehnungen:** Sollen die Dehnungen im Abschluss (30 Sek. pro Seite) auch mit Timer laufen und sich selbst abhaken, inklusive Seitenwechsel-Signal?
3. **Haltedauer steigern:** Soll die App die Haltezeit von selbst erhöhen, wenn das Ziel erreicht wurde? Das gehört eigentlich zum späteren Feature „Steigerungsvorschläge“.

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| | | |
