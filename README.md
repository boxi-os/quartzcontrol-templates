# QuartzControl-Vorlagen

Die Vorlagenpakete, die [QuartzControl](https://github.com/boxi-os/Quartz-GUI) beim Anlegen eines
Projekts anbietet. Ein `.qtpl` ist ein ZIP mit elf Bausteinen — Farben, Schriften, CSS-Variablen,
Stylesheets, Frames, Layout, Plugins, Theme, Übersetzungen, Presets und, bei dieser Vorlage, dem
Inhalt.

Dieses Repository ist öffentlich, weil die App die Datei ohne Anmeldung lesen können muss. Sie holt
sie über `raw.githubusercontent.com`, legt sie einen Tag lang zwischen und fällt auf die im
Programm mitgelieferte Kopie zurück, wenn kein Netz da ist. Eine Änderung hier erreicht also das
nächste angelegte Projekt, ohne dass ein neues Programm gebaut werden muss.

## Was drin ist

### `minimal-lesbar.qtpl`

**Minimal & lesbar** — eine vollständige Gestaltung, gedacht als Ausgangspunkt und als Nachschlage-
werk zugleich:

- **Farben, die gemessen sind.** 87 Text-auf-Grund-Paare, alle über der WCAG-AA-Schwelle, in hell
  und dunkel. Auch die dreizehn Callout-Typen, deren Standardfarben elfmal daran scheitern.
- **Drei eigene Seitenraster** für Inhalts-, Listen- und Fehlerseiten, auf einem Zwölf-Spalten-
  Raster, je für Desktop, Tablet und Telefon ausgelegt.
- **Selbst gehostete Schriften.** Instrument Sans, Inter und JetBrains Mono, vier Dateien,
  zusammen 157 KB. Es geht keine Anfrage an Google.
- **34 Stylesheets**, eines je Komponente, die alle ihre Farben und Maße aus 50 CSS-Variablen
  lesen — änderbar in der App unter *Stile → Variablen*.
- **Rund 270 Beispielseiten**, zweisprachig, die die Vorlage selbst erklären: zu jeder Komponente
  die Seite, auf der sie beschrieben ist. Beim Anlegen abwählbar.

### `latest.json`

Die Fassung, die QuartzControl für die aktuelle hält. Die App fragt sie beim Start ab und sagt auf
der Startseite Bescheid, wenn sie neuer ist als die laufende — mehr nicht: Es wird nichts geladen
und nichts installiert. Bekommt sie keine Antwort, sagt sie gar nichts, denn „konnte nicht prüfen"
ist nicht „alles aktuell".

```json
{ "version": "1.0.0-beta.1", "url": "https://…", "notes": "" }
```

`version` ist Semver, Vorabversionen eingeschlossen (`1.0.0-beta.2` ist neuer als `1.0.0-beta.1`,
`1.0.0` ist neuer als beide). `url` muss `https://` sein, sonst zeigt die App keinen Knopf. `notes`
ist ein kurzer Satz, der neben der Meldung steht — oder leer.

## Etwas ändern

Die Datei wird nicht von Hand gebaut. Sie entsteht aus dem Beispielprojekt heraus über
`npm run template:example` im QuartzControl-Repository, das dafür die gebaute App durch dieselben
Wege treibt, die ein Klick nimmt. Was hier liegt, ist das Ergebnis — hier eine neue Fassung
hineinlegen und committen genügt.

---

*English:* the template packages QuartzControl offers when creating a project. Public because the
app has to read the file without credentials; it falls back to a copy bundled with the app when
there is no network.
