# Smart Home

Der Administrator Ihres Home Assistant. Smart Home erledigt dort, was Sie in dessen Oberfläche tun
würden, schneller und einheitlicher: Er nimmt neue Geräte mit Ihnen auf, benennt alles nach dem
Schema, das Sie gewählt haben, schreibt Ihre Automationen und baut Ihre Dashboards — liest zuerst,
zeigt, was sich ändern wird, und bewahrt einen Rückweg.

## Was er tut

- **Neue Geräte**: „Hören Sie auf neue Geräte“ — er öffnet das Zigbee- (ZHA oder Zigbee2MQTT),
  Z-Wave- oder RFXCOM-Netz, hört, was hinzukommt, sagt Ihnen, was jedes Gerät ist, und fragt nach
  seinem Namen, seinem Raum und dem, was ausgeblendet werden soll. Dann schließt er das Netz.
- **Namen**: Er schlägt Namensschemata mit Beispielen aus Ihrem eigenen Haus vor —
  `light.lustre_salon`, `binary_sensor.do_entree` — oder übernimmt Ihres, benennt im Stapel um und
  repariert die Automationen und Dashboards, die die alten Kennungen nannten.
- **Räume, Etagen, Labels**: angelegt, aufgeräumt, jedes Gerät an seinem Platz.
- **Automationen, Skripte, Szenen, Helfer**: Sie sagen „wenn nachts die Haustür aufgeht, den Flur
  drei Minuten beleuchten“; er formuliert es neu, prüft jede Entität, validiert, legt an und
  testet mit Ihrer Zustimmung.
- **Dashboards**: nach Nutzung und Bildschirm — ein Telefon, ein Wandtablet —, als neue
  Dashboards, nie über Ihre hinweg, ohne die vorherige Fassung aufzubewahren.
- **Der Alltag**: „Wohnzimmer ausschalten“, „wie warm ist es oben“.
- **Der Zustand**: was Home Assistant meldet, Integrationen mit Fehler, nicht verfügbare
  Entitäten, schwache Batterien, stumme Geräte, wartende Updates.

Er rät nie eine Kennung, lässt nie ein Netz offen, speichert kein Passwort und kann Home Assistant
weder anhalten noch dessen Maschine herunterfahren.

## Was er braucht

Ein importierter Agent kommt ohne Rechte über die Standardrechte hinaus. Auf seiner Agent-Seite:

| Einstellung | Warum |
|---|---|
| **Aktivierte externe Dienste: Home Assistant** | Legen Sie den Dienst „Home Assistant“ an (Seite Dienste), mit der Adresse Ihrer Installation und einem langlebigen Zugriffstoken eines Administrators (in Home Assistant: Ihr Profil → Sicherheit → Langlebige Zugriffstoken), testen Sie ihn und erlauben Sie Smart Home, ihn zu nutzen. Das Token bleibt in Allkin. |
| **Externe Dienste nur lesend**: aus | Eingeschaltet kann Smart Home nur lesen und zuhören. |
| **Fähigkeit: Home-Assistant-Administration** | Seine Methode; wird heruntergeladen, wenn Sie sie ihm geben. |
| **Darf Aktionen planen** + Fähigkeit **Aktionen verwalten** | Für eine wöchentliche Zustandsprüfung. Sie geben jede Aktion frei, die er anlegt. |
| **Darf im Web suchen und Seiten lesen** | Um die Anleitung eines Geräts oder dessen Kopplungsgeste nachzuschlagen. Optional. |
| **Gedächtnis** (standardmäßig an) | Um Ihre Vorlieben zu behalten. |

## Was Sie sehen werden

Das Lesen Ihrer Installation verlangt nichts von Ihnen. **Jede Änderung zeigt eine Freigabekarte**
in der Unterhaltung — eine Umbenennung, ein Raum, ein gespeichertes Dashboard, ein geöffnetes
Netz —, eine einzige für den ganzen Stapel, und Sie können für die Sitzung freigeben. Der Schalter
**„Ohne Freigabe handeln“** des Dienstes hebt die Karten für alle Agenten auf, auch wenn niemand
da ist: Lassen Sie ihn aus, es sei denn, eine Aktion soll Ihre Installation von selbst ändern.

## So nutzen Sie ihn

1. Legen Sie den Dienst Home Assistant an und erlauben Sie ihn auf der Seite von Smart Home.
2. Sagen Sie: „Sehen Sie sich meine Installation an.“ Er geht sie durch, sagt Ihnen, was er
   gefunden hat, und fragt, womit Sie beginnen möchten.
3. Bitten Sie dann in Ihren Worten: „Hören Sie auf neue Zigbee-Geräte“, „benennen Sie die Küche
   ordentlich um“, „bauen Sie ein Dashboard für das Tablet im Flur“.

## Grenzen

- Von Hand in YAML geschriebene Dateien (`configuration.yaml`, Packages, Dashboards im YAML-Modus)
  sind für ihn nicht erreichbar: Er sagt Ihnen, was dort zu ändern ist.
- Eine Integration, die ein Konto oder ein Passwort verlangt, fügen Sie selbst hinzu, in Home
  Assistant.
- Er sieht weder, wie ein Dashboard aussieht, noch ob eine Lampe wirklich angegangen ist: Er fragt
  Sie.
