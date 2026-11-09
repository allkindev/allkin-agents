# Orchestrator

Ihre zentrale Anlaufstelle, wenn Sie nicht überlegen möchten, welchen Agenten Sie fragen sollen,
oder wenn eine Arbeit mehrere braucht. Orchestrator versteht die Anfrage, teilt sie bei Bedarf auf,
übergibt jeden Teil an den am besten geeigneten Agenten, prüft die Ergebnisse und gibt Ihnen eine
einzige Antwort.

## Was er tut

- Er wählt den richtigen Agenten für eine Anfrage und übergibt sie mit einem Auftrag, der für sich
  allein steht: das Ziel, die Aufgabe, das Material, das erwartete Ergebnis.
- Er koordiniert mehrere Agenten an einer Arbeit, in der richtigen Reihenfolge, und reicht das
  Ergebnis des einen an den nächsten weiter.
- Er liest jede Antwort als Prüfer: Unvollständiges, Widersprüchliches oder Ungeprüftes geht einmal
  zurück und wird Ihnen dann so gemeldet, wie es ist.
- Er gibt Ihnen eine einzige Antwort – zuerst das Ergebnis, dann wer was getan hat und was offen
  bleibt –, nie die Antworten untereinander eingefügt.
- Er sagt Ihnen, wenn kein Agent passt, und welches Agentenmodell passen würde.
- Er merkt sich, wer was gut kann, und Ihre Vorgaben.

## Was er braucht

Ein importierter Agent kommt ohne Rechte außer den Standardrechten. Auf seiner Agentenseite:

| Einstellung | Wozu |
|---|---|
| **Darf mit anderen Agenten kommunizieren** (standardmäßig an) | Das ist seine ganze Aufgabe. Sie können es auf eine Liste von Agenten beschränken. |
| **Gedächtnis** (standardmäßig an) | Um zu lernen, wer was gut kann, und Ihre Vorgaben. |

Mehr braucht er nicht: keinen Systemzugriff, kein Web. Je mehr spezialisierte Agenten Sie haben –
Writer, Researcher, Analyst, Developer … –, desto nützlicher ist er.

## So verwenden Sie ihn

1. Wenden Sie sich an Orchestrator wie an einen Assistenten, der das ganze Team kennt.
2. Bei einer größeren Arbeit nennt er Ihnen vor dem Start seinen Plan in wenigen Zeilen.
3. Sie erhalten eine einzige Antwort, mit den Pfaden der erzeugten Dateien.

## Gut zu wissen

Ein von Orchestrator aufgerufener Agent arbeitet, ohne dass jemand davor sitzt: Was Ihre Zustimmung
bräuchte (ein Befehl auf der Maschine, eine Veröffentlichung), kann dort abgelehnt werden.
Orchestrator sagt Ihnen dann, welchen Agenten Sie direkt fragen sollen, mit der fertigen Anfrage
zum Einfügen. Er gewährt nie ein Recht, weder sich selbst noch einem anderen Agenten.
