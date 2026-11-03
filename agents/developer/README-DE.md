# Developer

Ein Entwickler, der wie Claude Code arbeitet, innerhalb von Allkin: Er erkundet den Code, bevor er
ihn anfasst, plant in wenigen Zeilen, ändert so wenig, wie die Aufgabe verlangt, prüft durch die
Tests und den Build des Projekts und berichtet klar — was sich geändert hat, was geprüft wurde, was
bleibt.

## Was er tut

- Er liest ein Projekt wie ein Ingenieur, der dazukommt: wie es gebaut und getestet wird, seine
  Konventionen, den Code rund um die Änderung.
- Er behebt Fehler (reproduzieren, lokalisieren, beheben, beweisen), ergänzt Funktionen, schreibt
  Tests, refaktoriert auf Wunsch, schreibt Skripte, Konfiguration, Migrationen und Dokumentation.
- Er führt die Prüfungen aus — Tests, Typprüfung, Lint, Build — und liest ihr Ergebnis, bevor er
  etwas als erledigt meldet.
- Er prüft Code mit der Fähigkeit **Code-Review**: Befunde nach Schwere geordnet, jeder mit Zeile
  und einem konkreten Fehlerfall.
- Er hält git sauber: liest die Historie, committet nur auf Wunsch, schreibt sie nie um.

## Was er braucht

Ein importierter Agent kommt ohne jedes Recht an. Developer arbeitet am besten mit, auf seiner
Agentenseite:

| Einstellung | Warum |
|---|---|
| **Systemzugriff: Administrator** (Befehle) | Um Tests, Build, git und den Paketmanager auszuführen. Jeder Befehl wird Ihnen zuerst auf einer Karte gezeigt; Sie können einen für die Sitzung oder per Muster genehmigen. |
| **Webzugriff** | Um die Dokumentation einer Bibliothek oder eine Fehlermeldung zu lesen, die niemand versteht. |
| **Teilaufgaben** | Um eine große Codebasis parallel zu erkunden. |
| **Gedächtnis** (standardmäßig an) | Um sich zu merken, wie ein Projekt gebaut wird und welche Entscheidungen Sie getroffen haben. |
| **Fähigkeit: Code-Review** | Für Reviews; wird heruntergeladen, wenn Sie sie zuweisen. |

## So verwenden Sie ihn

1. Öffnen Sie ein Gespräch mit Developer und setzen Sie **den Arbeitsordner** (die Pille der
   Sendeleiste) auf das Projekt: Dort landen seine Dateien und Befehle.
2. Bitten Sie um die Änderung wie einen Kollegen: den Fehler, den Sie sehen, die gewünschte
   Funktion, die zu prüfende Datei. Er fragt nur per Formular nach, wenn eine echte Wahl offen ist.
3. Lesen Sie seinen Bericht: zuerst das Ergebnis, dann was sich geändert hat und was geprüft wurde.

## Sicherheit

Jeder Befehl geht durch Ihre Genehmigung. Developer lädt nie herunter und führt in einem Zug aus,
schaltet nie eine Schutzmaßnahme ab, damit etwas funktioniert, führt nie einen zerstörerischen
Befehl aus — Löschen außerhalb seines Entwurfsordners, Leeren einer Datenbank, Umschreiben der
git-Historie — ohne Ihre ausdrückliche, konkrete Anweisung, und kopiert nie ein Geheimnis, auf das
er stößt. Was er nicht hat, ist eine Einstellung von Allkin; er sagt Ihnen welche.
