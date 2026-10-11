# Architektur und Datenschutz-Leitlinien

**Stand:** 2026-10-12
**Bezug:** Sprachgespräch 2026-10-12

> **Hinweis:** Dies ist ein Zielbild mit Leitlinien, kein beschlossenes Feature. Die konkrete Umsetzung wird später als eigenes Feature spezifiziert und folgt dem üblichen [Prozess](prozess.md).

## Zweck

Dieses Dokument hält die angestrebte technische Architektur und die Datenschutz-Leitlinien für alle Apps in diesem Repo fest. Es trennt klar zwischen dem **Ist-Stand heute** und dem **Zielbild**.

## Ist-Stand heute

Bewusst minimal:

- **Eine Datei pro App:** Jede App ist eine einzelne HTML-Datei, z. B. [`comeback-training/index.html`](../comeback-training/index.html). Es gibt keinen Build-Schritt.
- **Daten nur lokal:** Alle persönlichen Daten liegen ausschließlich lokal im Browser (localStorage). Nichts verlässt das Gerät.
- **Statische Auslieferung:** Die Apps werden statisch über GitHub Pages ausgeliefert. Es gibt keinen Server und keine laufenden Kosten.

Folgen, wie im [Fachkonzept](../comeback-training/fachkonzept.md#datenhaltung-entschieden-2026-10-11) beschrieben:

- Die Daten gibt es nur auf dem Gerät und in dem Browser, in dem trainiert wird.
- Beim Leeren der Browserdaten gehen sie verloren.
- Sie hängen an der Adresse, unter der die App läuft.

## Zielbild und Leitlinien

Von Fabian vorgegeben, noch nicht umgesetzt.

1. **Kein zentraler Datenspeicher:** Es gibt keinen zentralen Server, auf dem persönliche Trainingsdaten liegen, weder im Klartext noch als Zwischenspeicher.
2. **Gerät zu Gerät:** Daten werden zwischen den eigenen Geräten direkt ausgetauscht, Peer-to-Peer. Das gilt auch, wenn Daten künftig an andere Apps übergeben werden.
3. **Ende-zu-Ende-Verschlüsselung:** Sobald Daten das Gerät verlassen, sind sie verschlüsselt und nur für die berechtigten eigenen Geräte lesbar. Das betrifft die Übertragung an andere Geräte oder Apps, das Teilen und den Export.
4. **Zero Trust:** Keiner Komponente in der Mitte wird vertraut. Ist zur Verbindungsaufnahme der Geräte ein Vermittler nötig (Signaling), darf dieser ausschließlich die Verbindung herstellen und sieht **nie** Klartext-Daten.
5. **Lokale Verschlüsselung:** Eine Verschlüsselung der Daten auf dem Gerät wird erwogen. Bei rein lokalem Betrieb bietet sie aber nur begrenzten Schutz, weil der Schlüssel ebenfalls lokal verfügbar sein muss. Wer das entsperrte Gerät und den Browser hat, kommt an beides. Ihren vollen Nutzen entfaltet Verschlüsselung erst, wenn Daten das Gerät verlassen: bei Übertragung, Export oder einem späteren Backend.

## Offene Fragen

> **Noch zu klären, bevor daraus ein Feature wird.**

1. **Technischer Weg für Gerät zu Gerät:**
   - **Direktverbindung:** z. B. WebRTC, mit einem Signaling-Dienst, der nur vermittelt und verschlüsselte Daten nie entschlüsseln kann.
   - **Austausch ohne Live-Verbindung:** z. B. über verschlüsselte Dateien, QR-Code oder Link.
2. **Kopplung (Pairing):** Wie werden die berechtigten Geräte miteinander gekoppelt, und wie werden die Schlüssel sicher ausgetauscht, z. B. per QR-Code von Gerät zu Gerät?
3. **Verhältnis zu Export und Import aus 001:** Die Sicherungsdatei aus [Feature 001](../comeback-training/features/001-ist-leistung-erfassen.md) könnte, verschlüsselt, ein erster, einfacher Weg von Gerät zu Gerät sein. Soll der Export deshalb von Anfang an verschlüsselt sein?
4. **GitHub Pages:** Pages liefert nur statische Dateien aus. Ein Signaling-Dienst wäre dort nicht hostbar. Wo liefe er, und wie bleibt er im Sinne von Zero Trust ohne Einblick in die Daten?
5. **Vertrauen in den App-Code:** Auch bei Ende-zu-Ende-Verschlüsselung läuft die Entschlüsselung im Code der App. Wer die ausgelieferte Seite verändern kann, könnte Daten im Klartext lesen. Wie wird sichergestellt, dass genau der Code aus diesem Repo ausgeliefert wird?
6. **Austausch mit anderen Apps:** Welche Apps sind gemeint, und in welchem Format werden Daten übergeben, ohne die Leitlinien 1–4 zu verletzen?
