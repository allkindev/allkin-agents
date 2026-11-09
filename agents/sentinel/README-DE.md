# Sentinel

Wacht über Ihre Server. Sentinel macht seine Runde auf den Maschinen, die Sie ihm anvertrauen, mit
Befehlen, die nichts verändern, vergleicht mit dem letzten Mal und sagt Ihnen, was Ihre
Aufmerksamkeit braucht, bevor daraus ein Ausfall wird: die Festplatte, die vollläuft, das
Zertifikat, das in zehn Tagen abläuft, das Backup, das seit drei Wochen stillsteht.

## Was er tut

- **Runden**: Festplatte, Speicher und Last, Dienste, die laufen müssen, ausstehende und
  Sicherheitsupdates, erforderlicher Neustart, Zertifikate, Backups, fehlgeschlagene Anmeldungen
  und offene Ports, Fehler in den Protokollen.
- **Trends**: Er bewahrt die Messwerte jeder Runde auf und sagt Ihnen, wohin sie führen – „`/var`
  bei 91 %, in etwa zehn Tagen voll“.
- **Ein Bericht nach Dringlichkeit**: kritisch, Warnung, Hinweis; „alles in Ordnung“ ist eine
  Zeile. Jeder Befund kommt mit dem genauen Befehl, den er vorschlägt – und nur ausführt, wenn Sie
  es verlangen.
- **Ein Blatt pro Maschine**: was dort laufen muss, was dort normal ist, Ihre Schwellenwerte.
- **Störungen**: Wenn etwas ausfällt, eine schrittweise Diagnose und ein schriftlicher Bericht.
- **Selbstständig** über die Aktionen von Allkin: eine Runde jeden Morgen oder jede Woche.

Er repariert nie von sich aus, fährt nie eine Maschine herunter, liest nie ein Geheimnis.

## Was er braucht

Ein importierter Agent kommt ohne Rechte außer den Standardrechten. Auf seiner Agentenseite:

| Einstellung | Wozu |
|---|---|
| **Dienste: Ihre Maschinen per SSH** | Legen Sie pro Server einen Dienst „Maschine per SSH“ an (Seite Dienste), testen Sie ihn und erlauben Sie Sentinel die Nutzung. Die Zugangsdaten bleiben in Allkin. |
| **Systemzugriff: Nur lesen** | Um die Maschine, auf der Allkin läuft, rein lesend und ohne Genehmigung zu prüfen. |
| **Darf Aktionen planen** + Fähigkeit **Aktionen verwalten** | Für regelmäßige Runden. Sie genehmigen jede Aktion, die er anlegt. |
| **Fähigkeiten: Server-Gesundheitscheck, Störungsbericht** | Seine Methoden; heruntergeladen, wenn Sie sie ihm geben. |
| **Gedächtnis** (standardmäßig an) | Um Ihre Maschinen und Schwellenwerte zu behalten. |

### Runden ohne Sie

Jeder Befehl auf einer Maschine per SSH zeigt Ihnen eine Karte; Sie können für die Sitzung
genehmigen oder Muster auf der Seite von Sentinel speichern. Eine Runde, die **von einer Aktion
gestartet** wird, ohne dass jemand davor sitzt, läuft nur auf Maschinen, deren Dienst den Schalter
**„Ohne Freigabe handeln“** eingeschaltet hat. Dieser Schalter lässt Sentinel dort selbstständig
Befehle ausführen: Schalten Sie ihn nur für ein **SSH-Konto ein, das auf dieser Maschine nur lesen
kann** (ein gewöhnlicher Benutzer ohne sudo, Mitglied der Gruppen, die die Protokolle lesen).

## So verwenden Sie ihn

1. Legen Sie die SSH-Dienste an und erlauben Sie sie auf der Seite von Sentinel.
2. Bitten Sie: „Machen Sie eine erste Runde.“ Er erkundet jede Maschine, schreibt ihr Blatt und
   fragt Sie einmal, was er nicht beobachten kann: was laufen muss, wohin die Backups gehen.
3. Nehmen Sie die Aktion an, die er für regelmäßige Runden vorschlägt, oder bitten Sie „Machen Sie
   Ihre Runde“, wann Sie möchten.
4. Wenn er etwas meldet, entscheiden Sie: Er nennt den Befehl; Sie sagen Ja oder führen ihn selbst
   aus.
