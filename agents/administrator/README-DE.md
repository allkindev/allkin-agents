# Administrator

Der Administrator der Maschine, auf der Allkin läuft, und von Allkin selbst. Root über `sudo`,
installiert und entfernt er Software, aktualisiert das System, verwaltet Dienste, Benutzer,
Festplatten, Firewall-Regeln und SSH, schreibt Automatisierungsskripte und erstellt die Aktionen
von Allkin — welches System auch immer: Debian, Ubuntu, Fedora, RHEL, Arch, openSUSE, Alpine,
Void, Gentoo, mit oder ohne systemd, in einem Container oder unter WSL.

## Was er tut

- **Software**: installiert, aktualisiert und entfernt sie aus vertrauenswürdigen Quellen (zuerst
  die Distribution), sagt, woher sie kommt und wie sie aktuell gehalten wird.
- **Systemupdates**: zeigt, was sich ändert, Sicherheit zuerst, spielt sie ein und sagt Ihnen, ob
  ein Neustart nötig ist und warum.
- **Dienste, Benutzer, Festplatten, Netzwerk**: startet, stoppt, aktiviert, räumt auf — sichert
  jede Datei, die er ändert, und prüft eine Konfiguration, bevor er sie neu lädt.
- **Firewall und SSH**: öffnet, schließt, schränkt ein — in der Firewall, die die Maschine bereits
  nutzt, ohne je Ihren Zugang abzuschneiden, mit vorbereitetem Rückweg vor jeder riskanten
  Änderung.
- **Automatisierungsskripte**: ohne Schaden wiederholbar, mit Probelauf, Protokoll und
  Benachrichtigung bei einem Fehler; Sie starten sie als Verknüpfung, oder eine Allkin-Aktion
  führt sie aus.
- **Allkin**: Er kennt es in- und auswendig — Dokumentation, Dienst, Protokolle, Updates,
  Sicherungen, Ereignisprotokoll, Seiten und Einstellungen. Fragen Sie ihn, wie etwas in Allkin
  geht: Er antwortet und führt Sie Schritt für Schritt. Aktionen und Agenten erstellt er selbst; für das,
  was Ihnen zusteht (Rechte, Einstellungen, die Installation einer Integration), gibt er Ihnen den
  genauen Weg in der Oberfläche.
- **Ein Datenblatt der Maschine und ein Protokoll jeder Änderung** in seinem Ordner: was
  installiert ist, wie Sie die Maschine erreichen, was wann geändert wurde und wie man es
  rückgängig macht.

Er schaltet die Maschine nie aus, vergibt nie ein Recht (weder sich selbst noch einem anderen
Agenten), ändert die Konfiguration von Allkin nie von Hand, rührt das Ereignisprotokoll nie an,
hebt nie die Schutzmechanismen von Allkin für Firewall und SSH auf, lädt nie ein Skript herunter
und führt es in einem Zug aus.

## Was er braucht

Ein importierter Agent kommt ohne Rechte über die Voreinstellungen hinaus. Auf seiner
Agentenseite:

| Einstellung | Warum |
|---|---|
| **Systemzugriff: Systemadministrator** | Sein Beruf: jeder Befehl, Root über `sudo`. Jeder Befehl wird Ihnen zuerst auf einer Karte gezeigt. |
| **Darf Aktionen planen** + Fähigkeit **Aktionen verwalten** | Um die Aktionen von Allkin zu erstellen. Sie bestätigen jede Erstellung und jede Löschung. |
| **Darf andere Agenten erstellen, neu prompten und löschen** | Um Agenten für Sie zu erstellen (ohne jedes Recht geboren) und ihre Rollen aktuell zu halten. |
| **Darf im Web suchen und Seiten lesen** | Um die Dokumentation einer Software, Versionshinweise oder eine Sicherheitsmeldung zu lesen. |
| **Darf Teilaufgaben starten** | Um lange Protokolle oder Konfigurationen durchzugehen, ohne sein Gespräch zu füllen. |
| **Gedächtnis** (standardmäßig an) | Um sich zu merken, wie Sie die Maschine erreichen, und welche Entscheidungen Sie getroffen haben. |
| **Fähigkeiten: Systemadministration, Allkin-Administration, Störungsbericht** | Seine Methoden; heruntergeladen, wenn Sie sie ihm geben. |

### Root, und die Karten

Allkin läuft unter dem Benutzer `allkin`, der `sudo` ohne Passwort nutzen darf: Administrator ist
Root. **Jeder Befehl geht trotzdem über seine Karte** — Freigeben, **Für diese Sitzung
freigeben** (alle Befehle dieses Gesprächs, praktisch für eine lange Arbeit), **Immer
erlauben …** (ein auf seiner Seite gespeichertes Muster) oder Ablehnen. Diese Karte ist die Mauer
von Allkin, keine Wahl des Agenten: Kein Agent kann sie entfernen.

### Automatisierungen ohne Sie

Eine Aktion, die Administrator weckt, während niemand da ist, kann Befehle nur ausführen, wenn
Sie die **automatische Bestätigung** dieser Aktion einschalten (auf der Seite der Aktion) und
seine Seite diese Befehle automatisch bestätigt. Ein regelmäßig auszuführendes Skript ist
einfacher: Administrator schreibt es und gibt Ihnen den Befehl; Sie erstellen die Aktion, die es
ausführt (Aktionen › Neue Aktion), oder fügen es als Verknüpfung hinzu.

## So verwenden Sie ihn

1. Geben Sie ihm die Rechte oben und die Fähigkeiten.
2. Bitten Sie: „Lernen Sie diese Maschine kennen.“ Er erkennt das System, schreibt das Datenblatt
   der Maschine und fragt Sie einmal, was er nicht beobachten kann — wie Sie die Maschine
   erreichen, was weiterlaufen muss.
3. Dann bitten Sie um alles Weitere: „Installieren Sie nginx und öffnen Sie Port 443“,
   „Aktualisieren Sie das System“, „Schließen Sie alles außer SSH aus meinem Netz“, „Jeden
   Sonntagabend die Protokolle aufräumen“, „Warum ist Allkin langsam?“.
4. Geben Sie auf den Karten frei — einmal oder für die Sitzung.
