# Migrator

Ein Agent, der Ihre Agenten aus **OpenClaw** (früher Clawdbot, Moltbot) oder **NanoClaw** in
Allkin holt. Geben Sie ihm ein Zip Ihrer alten Installation: Er lässt die Geheimnisse zurück,
schreibt Rolle und Gedächtnis jedes Agenten für Allkin neu, wandelt seine Fähigkeiten um und gibt
Ihnen ein Archiv pro Agent zum Importieren, mit einer kurzen Liste dessen, was noch zu tun ist.

Ziel ist eine gute Migration, keine perfekte Kopie: Was einfach in Allkin passt, wird übernommen,
der Rest wird für Sie aufgelistet.

## Was er tut

- Er erkennt eine OpenClaw- oder NanoClaw-Installation (beide Aufbauten von NanoClaw) und listet,
  was sie enthält: Agenten, Rollen, Gedächtnisse, Notizen, Fähigkeiten, geplante Aufgaben, Kanäle.
- Er fragt Sie mit einem einzigen Formular, was migriert werden soll.
- Er schreibt eine Rolle pro Agent aus seiner Identität, seiner Seele und seinen Regeln; seine
  dauerhaften Fakten behält er als Gedächtnis, seine Notizen als Dateien.
- Er wandelt die Fähigkeiten in ein Repository um, das Sie in den Einstellungen hinzufügen;
  Skripte, die in Allkin nicht laufen können, werden mit Begründung beiseitegelegt.
- Er listet die anzulegenden Aktionen, die zu verbindenden Services und Kanäle, die zu
  erteilenden Rechte.

## Was er braucht

| Einstellung | Warum |
|---|---|
| **Fähigkeit: Agenten migrieren** | Seine ganze Methode und seine Skripte; beim Anlegen des Agenten heruntergeladen. |
| **Gedächtnis** (standardmäßig an) | Um sich zu merken, was er migriert hat. |

Sonst nichts: Er arbeitet in seinem eigenen Ordner. Wenn Sie ihm das Recht „Darf Aktionen planen"
und die Fähigkeit „Aktionen verwalten" geben, kann er die Aktionen auch selbst anlegen, jede von
Ihnen freigegeben.

## So verwenden Sie ihn

1. Erstellen Sie auf dem alten Rechner ein Zip der Installation:
   - OpenClaw: `cd ~ && zip -r openclaw.zip .openclaw -x '.openclaw/agents/*/sessions/*' '*/node_modules/*'`
   - NanoClaw: `zip -r nanoclaw.zip nanoclaw -x '*/node_modules/*' 'nanoclaw/data/sessions/*'`
2. Öffnen Sie eine Unterhaltung mit dem Migrator, hängen Sie das Zip an und bitten Sie ihn um die
   Migration.
3. Beantworten Sie sein Formular und folgen Sie seiner Liste: Importieren Sie jedes Archiv (das „+"
   der Agentenliste › Agent importieren), fügen Sie das Repository der Fähigkeiten hinzu, erteilen
   Sie Rechte, verbinden Sie Services.

## Sicherheit

Zugangsdaten, Transkripte und die Werte der `.env` werden nie entpackt; jedes Token und jeder
Schlüssel der Konfiguration wird ersetzt; ein Archiv wird abgelehnt, solange etwas übrig bleibt,
das wie ein Geheimnis aussieht. Der Code der alten Plattform wird gelesen, nie ausgeführt. Jeder
importierte Agent kommt ohne jedes Recht an und durchläuft die Identitätskarte und ihren
Prüfen-Knopf wie jeder Import. Löschen Sie das Zip aus dem Ordner `Upload/` des Agenten, wenn Sie
fertig sind.
