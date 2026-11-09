# Analyst

Bringt Tabellen zum Sprechen. Geben Sie Analyst einen Export – Umsätze, Rechnungen,
Stundenzettel, Umfrageantworten, Lagerbestand – und eine Frage, auch eine vage. Er prüft, was die
Datei wirklich enthält, berechnet jede Zahl per Skript und übergibt Ihnen eine kurze Notiz: was die
Zahlen zeigen, was sie nicht zeigen, und die Tabelle und das Diagramm, die es belegen.

## Warum seine Zahlen verlässlich sind

Ein Sprachmodell, das zweihundert Zeilen liest und ihre Summe nennt, rät. Analyst tut das nie: Jede
Summe, jeder Mittelwert, jede Anzahl und jeder Prozentwert stammt aus einem Skript, das die ganze
Datei liest und exakt rechnet, auf den Cent genau. Die Aufgabe des Modells ist, den Daten die
richtigen Fragen zu stellen und zu sagen, was die Antworten bedeuten.

## Was er tut

- **Er liest** CSV-, TSV- und Excel-Dateien (.xlsx); er erkennt das Trennzeichen, das
  Dezimalkomma, die Reihenfolge der Datumsangaben.
- **Er prüft zuerst**: leere Zellen, Text zwischen Zahlen, doppelte Zeilen, unterschiedlich
  geschriebene Werte, mehrdeutige Daten – und sagt es Ihnen vor dem Rechnen.
- **Er rechnet**: Summen, Mittelwerte und Mediane, Anzahlen, Anteile, nach Kategorie, Kunde, Monat,
  Quartal oder Woche, mit Filtern; Differenzen und Veränderungsraten.
- **Er zeichnet** schlichte Diagramme – Balken, Querbalken, Linien – als SVG-Dateien.
- **Er schreibt die Notiz**: zuerst die Antwort, drei bis fünf Befunde mit ihren Zahlen, was
  ausgelassen wurde, was sich nicht schließen lässt. Auf Wunsch die Ergebnisse als Excel-Datei.

## Was er braucht

Ein importierter Agent kommt ohne Rechte außer den Standardrechten. Auf seiner Agentenseite:

| Einstellung | Wozu |
|---|---|
| **Fähigkeit: Datenanalyse** | Seine Methode und seine Skripte. Sie laufen in einem geschlossenen Rahmen: nur Node, kein Netzwerk, Lesen und Schreiben nur im eigenen Ordner. Der erste Lauf zeigt Ihnen eine Karte; Sie können die Skripte dieser Fähigkeit für die Sitzung oder dauerhaft freigeben. |
| **Gedächtnis** (standardmäßig an) | Um zu behalten, wie Ihre Exporte aufgebaut sind, und Ihre Definitionen – nie Ihre Zahlen. |

Er braucht weder Systemzugriff noch Web noch einen Dienst.

## So verwenden Sie ihn

1. **Hängen Sie die Datei** an Ihre Nachricht an (sie muss im Ordner von Analyst liegen, damit die
   Skripte sie lesen) und stellen Sie Ihre Frage: „Hier sind die Rechnungen 2026 – wer sind unsere
   zehn besten Kunden und welchen Anteil am Umsatz machen sie aus?“
2. Er sagt Ihnen, was die Datei ist und was zweifelhaft ist, und fragt einmal, was er nicht wissen
   kann.
3. Sie erhalten die Notiz mit den Pfaden der Ergebnistabellen und Diagramme.

## Grenzen

Eine Tabelle auf einmal: Er verknüpft keine zwei großen Dateien und baut kein statistisches Modell.
`.xls`- und OpenDocument-Dateien müssen zuerst als `.xlsx` oder `.csv` gespeichert werden. Eine
Formel in einer Arbeitsmappe liefert das Ergebnis, das die Datei beim letzten Speichern behalten
hat.
