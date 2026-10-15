# 004 – Muskelkarte am Körpermodell

**Status:** Abgestimmt (Freigabe Fabian, 2026-10-15)
**Erstellt:** 2026-10-11 · **Überarbeitet:** 2026-10-12
**Bezug:** Handzettel „Körper/Dummy SVG Darstellung welche Muskeln wie bewegt werden“
**Siehe auch:** [008 – Bewegungsdarstellung der Übungen](008-bewegungsmodell.md), dort liegt der Teil „wie bewegt werden“

## Problem

Die beanspruchten Muskeln stehen heute nur als Text da. Ob man „Rhomboiden“ oder „mittlerer Gesäßmuskel“ verortet bekommt, ist Glückssache, und ein Gefühl für die Übung entsteht daraus nicht.

## Ziel

Jede Übung zeigt an einer schematischen Körperfigur, welche Muskeln arbeiten. Haupt- und Hilfsmuskeln sind auf einen Blick unterscheidbar.

## Scope

**Drin:**
- Schematische, geschlechtsneutrale Körperfigur, Vorder- und Rückseite nebeneinander, als eigene, schlichte Zeichnung
- Hervorhebung pro Übung in zwei Stufen: Hauptmuskeln kräftig, Hilfsmuskeln hell
- Antippen einer Muskelregion zeigt ihren Namen
- Abschlussbild am Ende der Einheit: Gesamtkarte, welche Regionen heute trainiert wurden

**Nicht drin:**
- Anatomisch exakte Darstellung einzelner Muskelköpfe
- Darstellung der Bewegung in jeder Form, auch als Animation. Das ist bewusst ausgelagert in [008](008-bewegungsmodell.md).
- 3D-Modell

## Fachliche Regeln

1. **Regionen:** Die Figur kennt diese Regionen, passend zu den Übungen im Plan:

   | Vorderseite | Rückseite |
   |---|---|
   | Brust | Trapez / oberer Rücken |
   | Vordere Schulter | Hintere Schulter |
   | Seitliche Schulter | Rhomboiden / mittlerer Rücken |
   | Bizeps | Breiter Rückenmuskel (Latissimus) |
   | Gerader Bauchmuskel | Trizeps |
   | Querer Bauchmuskel (als Rumpf) | Unterer Rücken |
   | Hüftbeuger | Großer Gesäßmuskel |
   | Oberschenkelvorderseite (Quadrizeps) | Mittlerer / kleiner Gesäßmuskel |
   | Adduktoren | Hintere Oberschenkel |

2. **Zuordnung:** Jede im Plan genannte Muskelangabe wird genau einer oder mehreren Regionen zugeordnet. Sammelbegriffe wie „Rumpf“ heben Bauch und unteren Rücken hervor.
3. **Seitliche Übungen:** Bei einarmigen Übungen wird die Region beidseitig hervorgehoben, weil beide Seiten trainiert werden.
4. **Platz:** Die Figur ersetzt die Textzeile nicht. Der Text bleibt für Genauigkeit, die Figur dient dem schnellen Überblick. Auf dem Handy ist die Figur klein und lässt sich zum Vergrößern antippen.
5. **Farben:** Hauptmuskeln und Hilfsmuskeln sind auch ohne Farbsehen unterscheidbar, z. B. über Füllung gegenüber Schraffur.
6. **Aussehen der Figur:** Die Figur ist eine schlichte, geschlechtsneutrale Silhouette ohne Gesicht und ohne Details, die ein Geschlecht andeuten.
7. **Abschlussbild:** Nach „Einheit abschließen“ (001) zeigt die Zusammenfassung eine Gesamtkarte aller Regionen, die in dieser Einheit trainiert wurden.
   - Grundlage sind die tatsächlich gemachten Übungen, also auch gewählte Alternativen (007) und ein gemachter Burner (005). Aufwärmen und Abschluss zählen nicht mit.
   - Eine Region erscheint kräftig, wenn sie in mindestens einer Übung Hauptmuskel war, sonst hell, wenn sie nur als Hilfsmuskel beteiligt war.
   - Nicht trainierte Regionen bleiben neutral.
   - Bei einer abgebrochenen Einheit (001, Regel 9) zeigt das Abschlussbild nur die bis dahin erledigten Übungen.

## Akzeptanzkriterien

- [ ] Für jede Übung im Plan, inklusive Aufwärmen und Abschluss, zeigt die Figur die passenden Regionen.
- [ ] Haupt- und Hilfsmuskeln sind auf dem Handy auf einen Blick unterscheidbar, in hellem und dunklem Design.
- [ ] Antippen einer hervorgehobenen Region zeigt ihren Namen.
- [ ] Die Figur wirkt geschlechtsneutral.
- [ ] Nach „Einheit abschließen“ zeigt ein Abschlussbild alle heute trainierten Regionen, Haupt- und Hilfsmuskeln unterscheidbar, inklusive Alternativen und Burner.

## Offene Fragen

Keine.

## Entscheidungen

| Datum | Entscheidung | Begründung |
|---|---|---|
| 2026-10-12 | Muskelkarte nur als farbige Markierung (welche Muskeln arbeiten, Haupt- und Hilfsmuskeln), keine Bewegungsdarstellung. Der Wunsch nach Bewegung geht in das eigene Feature 008. | Die Markierung ist klein und schnell umsetzbar. Ein menschlich wirkendes Bewegungsmodell ist mit Abstand das aufwendigste Feature und wird getrennt in Ruhe geklärt. |
| 2026-10-12 | Gesamtkarte als Abschlussbild am Ende der Einheit | Schöner Abschluss: „das hast du heute alles bewegt“ |
| 2026-10-12 | Figur geschlechtsneutral, schlichte Silhouette | Wunsch Fabian, für die Muskelanzeige gleichwertig |
