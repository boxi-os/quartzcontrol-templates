# QuartzControl-Vorlagen

Die Vorlagenpakete, die [QuartzControl](https://github.com/boxi-os/QuartzControl) beim Anlegen eines
Projekts anbietet. Ein `.qtpl` ist ein ZIP mit zwölf Bausteinen — Farben, Schriften, CSS-Variablen,
Stylesheets, Frames, Layout, Plugins, Theme, Übersetzungen, Presets, die statischen Dateien und,
bei dieser Vorlage, dem Inhalt.

Dieses Repository ist öffentlich, weil die App die Datei ohne Anmeldung lesen können muss. Sie holt
sie über `raw.githubusercontent.com`, legt sie einen Tag lang zwischen und fällt auf die im
Programm mitgelieferte Kopie zurück, wenn kein Netz da ist. Eine Änderung hier erreicht also das
nächste angelegte Projekt, ohne dass ein neues Programm gebaut werden muss.

## Was drin ist

### `qc-basic.qtpl`

**Basis-Template** — die Vorlage, die die App beim Anlegen eines Projekts anbietet. Sie hat am
20. September `minimal-lesbar.qtpl` in dieser Rolle abgelöst, und der Grund ist, was ein neues
Projekt bekam: entweder ein fremdes Handbuch mit 301 Seiten oder, ohne das Häkchen, eine fertige
Gestaltung ohne einen einzigen Satz darin. Beides war das Falsche.

Dieselbe Gestaltung wie das Example — gemessene Farben, vier eigene Seitenraster, selbst
gehostete Schriften, alle 31 Stylesheets —, aber so wenig Inhalt wie möglich:

- **Je eigenem Plugin ein oder zwei Komponenten**, nicht sieben. Eine Marke im Kopf, ein Kasten
  in der Seitenleiste, eine Navigation links mit Schublade auf dem Telefon, ein Sprachumschalter.
  Ein Projekt, das mit fünf Kästen, einem Graphen und einer Tag-Leiste startet, wirft seinem
  Nutzer Arbeit hin, die er erst rückgängig machen muss.
- **Trotzdem alle 31 Stylesheets**, auch die der abgeschalteten Komponenten. Wer den Explorer,
  den Graphen oder die Tag-Leiste einschaltet, bekommt sie fertig gestaltet.
- **Zwanzig kurze Seiten in zwei Sprachen**, drei Ebenen tief. Sie zeigen, wie die Website
  aussieht, bevor eigene Notizen da sind, und sind zum Löschen gedacht. Beim Anlegen abwählbar.
- **60 CSS-Variablen**, darunter die dreizehn Callout-Farben — alle in der App unter
  *Stile → Variablen* änderbar.
- **Noto Sans und Noto Sans Mono**, drei Dateien, selbst gehostet. Es geht keine Anfrage an
  Google.

Zusammen 288 KB — gegen 764 KB der Vorlage darunter. **48 Plugin-Einträge, davon 33 aktiv**, vier
Frames, drei Gruppen, sieben Seitentypen, zwei Presets, elf Übersetzungen.

### `minimal-lesbar.qtpl`

**Example** — eine vollständige Gestaltung, gedacht als Ausgangspunkt und als Nachschlagewerk
zugleich.

**Diese Datei bleibt liegen, und zwar unverändert.** Jede App-Fassung, die vor dem 20. September
ausgeliefert wurde, fragt genau diesen Pfad ab; sie zu löschen oder zu überschreiben nähme allen
bestehenden Installationen ihre Online-Vorlage. Was unten steht, beschreibt den Stand vom
20. September morgens und wird nicht nachgezogen.

- **Farben, die gemessen sind.** 93 Text-auf-Grund-Paare, alle über der WCAG-AA-Schwelle, in hell
  und dunkel. Auch die dreizehn Callout-Typen, deren Standardfarben elfmal daran scheitern.
- **Vier eigene Seitenraster** für Inhalts-, Listen-, Fehler- und Zeichenseiten, auf einem
  Zwölf-Spalten-Raster, je für Desktop, Tablet und Telefon ausgelegt.
- **Selbst gehostete Schriften.** Instrument Sans, Inter und JetBrains Mono, vier Dateien,
  zusammen 158 KB. Es geht keine Anfrage an Google.
- **30 Stylesheets**, eines je Komponente, die alle ihre Farben und Maße aus 50 CSS-Variablen
  lesen — änderbar in der App unter *Stile → Variablen*.
- **53 Plugin-Einträge**, darunter sieben Instanzen desselben Layout-Box-Plugins: dieselbe
  Komponente an sieben Stellen, jede mit eigenen Optionen.
- **Ein Handbuch in sieben Kapiteln**, 266 Markdown-Seiten, zweisprachig, das die Vorlage selbst
  erklärt: zu jeder Komponente die Seite, auf der sie beschrieben ist. Beim Anlegen abwählbar.

Zusammen 764 KB.

- **Die statischen Dateien**, die dazugehören: die Textschnipsel, auf die eine der sieben
  Layout-Boxen zeigt, dazu was sonst unter `quartz/static/` liegt. Bis zum 6. September trug ein
  Paket davon nichts, und genau diese Box kam im neuen Projekt leer an.

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
