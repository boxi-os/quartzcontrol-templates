# Vorlagen für QuartzHub

Die Vorlagenpakete, die [QuartzHub](https://github.com/boxi-os/QuartzHub) beim Anlegen eines
Projekts anbietet, und vor ihm [QuartzControl](https://github.com/boxi-os/QuartzControl), das seit
dem 11. November eingestellt ist. Beide fragen dieselbe Adresse, deshalb trägt das Repository noch
QuartzControls Namen. Ein `.qtpl` ist ein ZIP mit zwölf Bausteinen —
Farben, Schriften, CSS-Variablen, Stylesheets, Frames, Layout, Plugins, Theme, Übersetzungen,
Presets, die statischen Dateien und, bei dieser Vorlage, dem
Inhalt.

Dieses Repository ist öffentlich, weil die App die Datei ohne Anmeldung lesen können muss. Sie holt
sie über `raw.githubusercontent.com` und legt sie einen Tag lang zwischen. QuartzHub liefert keine
eigene Kopie mit, denn ein neues Projekt klont Quartz ohnehin aus dem Netz; QuartzControl fiel auf
seine mitgelieferte zurück. Eine Änderung hier erreicht also das nächste angelegte Projekt, ohne
dass ein neues Programm gebaut werden muss.

## Was drin ist

### `qc-basic.qtpl`

**Basis-Template** — die Vorlage, die die App beim Anlegen eines Projekts anbietet. Sie hat am
20. September `minimal-lesbar.qtpl` in dieser Rolle abgelöst, und der Grund ist, was ein neues
Projekt bekam: entweder ein fremdes Handbuch mit 301 Seiten oder, ohne das Häkchen, eine fertige
Gestaltung ohne einen einzigen Satz darin. Beides war das Falsche.

Dieselbe Gestaltung wie das Example — gemessene Farben, vier eigene Seitenraster, selbst
gehostete Schriften, alle dreizehn Stylesheets —, aber so wenig Inhalt wie möglich:

- **Je eigenem Plugin ein oder zwei Komponenten**, nicht sieben. Eine Marke im Kopf — das
  Projektbild, in QuartzHub unter „Konfiguration → Website“ ersetzbar —, ein Kasten in der
  Seitenleiste, eine Navigation links mit Schublade auf dem Telefon, ein Sprachumschalter, ein
  Kontaktformular aus quartz-forms, das noch nichts sendet.
  Ein Projekt, das mit fünf Kästen, einem Graphen und einer Tag-Leiste startet, wirft seinem
  Nutzer Arbeit hin, die er erst rückgängig machen muss.
- **Trotzdem alle dreizehn Stylesheets**, auch für die abgeschalteten Komponenten. Wer den Explorer,
  den Graphen oder die Tag-Leiste einschaltet, bekommt sie fertig gestaltet.
- **Zweiundzwanzig kurze Seiten in zwei Sprachen**, drei Ebenen tief, eine davon mit dem Formular. Sie zeigen, wie die Website
  aussieht, bevor eigene Notizen da sind, und sind zum Löschen gedacht. Beim Anlegen abwählbar.
- **70 CSS-Variablen**, darunter die dreizehn Callout-Farben, die sechs, mit denen jede der
  beiden Seitenspalten stehen bleibt oder mit der Seite mitläuft, und die vier Flächen der
  Seitenspalten, des Kopfs und des Fußes — alle in der App unter *Stile → Variablen* änderbar.
- **Noto Sans und Noto Sans Mono**, drei Dateien, selbst gehostet. Es geht keine Anfrage an
  Google.

Zusammen 244 KB — gegen 764 KB der Vorlage darunter. **45 Plugin-Einträge, davon 31 aktiv**, vier
Frames, drei Gruppen, sieben Seitentypen, zwei Presets, elf Übersetzungen.

**Seit dem 11. November für Quartz 5.1.** Die Einträge, die 5.1 eingebaut hat (crawl-links,
remove-draft, content-index), sind draußen, ihre Werte waren ohnehin die Vorgaben von 5.1; ebenso
das veraltete hard-line-breaks, das schon abgeschaltet war. GitHub-Markdown läuft vor Obsidian-Markdown, wie 5.1 es verlangt. Die
Beispielseiten haben je Absatz eine Zeile, denn 5.1 macht wie Obsidian aus jedem einfachen
Zeilenumbruch einen sichtbaren Umbruch. In ein Projekt mit Quartz 5.0 lässt sie sich weiter
importieren: Ein Import entfernt keine Einträge des Projekts.

### `qc-example.qtpl`

**Example** — die Vorführung: dieselbe Gestaltung wie das Basis-Template, aber mit jeder
Komponente im Einsatz statt nur mit den nötigen, und mit dem Handbuch, das sie erklärt.

**Die App fragt diese Datei nicht.** Sie liegt hier für Menschen: wer die Vorführung ansehen oder
in ein bestehendes Projekt holen will, lädt sie herunter und nimmt in QuartzHub *Vorlagen → Vorlage
anwenden*.

- **Sieben Instanzen desselben Layout-Box-Plugins**, jede mit eigenen Optionen — dieselbe
  Komponente an sieben Stellen der Seite.
- **Zwei Navigationen** aus quartz-navigations: ein Akkordeon in der linken Spalte mit Schublade
  auf dem Telefon, ein Pager unter dem Text. Der Explorer ist abgeschaltet und bleibt gestaltet —
  ein Häkchen holt ihn zurück, wie er war.
- **Ein Handbuch in sieben Kapiteln**, 303 Inhaltsdateien, zweisprachig, das die Vorlage selbst
  erklärt: zu jeder Komponente die Seite, auf der sie beschrieben ist. Beim Import abwählbar.
- Sonst alles wie im Basis-Template: dreizehn Stylesheets, 70 CSS-Variablen, vier Frames, Noto Sans und
  Noto Sans Mono selbst gehostet, gemessene Kontraste.

51 Plugin-Einträge, davon 40 aktiv. Zusammen 692 KB — der Inhalt allein misst vor dem Packen 974 KB.

**Seit dem 14. November für Quartz 5.1 und mit QuartzHub erzeugt.** Wie im Basis-Template sind
crawl-links, remove-draft, content-index und das veraltete hard-line-breaks draußen, und
GitHub-Markdown läuft vor Obsidian-Markdown. Anders als dort behalten die Seiten ihren Umbruch bei
Spalte 100; dafür schaltet die Vorlage die strikten Zeilenumbrüche ein (`strictLineBreaks` von
Obsidian-Markdown), sonst machte 5.1 aus jedem Zeilenende einen sichtbaren Umbruch, gemessen
3.081 auf 228 Seiten. Das Handbuch nennt QuartzHub statt QuartzControl.

Zu sehen ist sie unter <https://boxi-os.github.io/Quartz-Example-Template/>.

### `minimal-lesbar.qtpl`

**Example, Stand 20. September morgens** — dieselbe Vorlage wie `qc-example.qtpl`, nur eingefroren.

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

Die Fassung, die QuartzControl für die aktuelle hält. QuartzHub fragt sie nicht; es fragt die
Release-Seite seines eigenen Repositorys. Die App fragt sie beim Start ab und sagt auf
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

Die Pakete werden nicht von Hand gebaut. Die Example-Vorlage entsteht in QuartzHub mit *Vorlagen →
Vorlage erstellen* am Beispielprojekt, und zwar jedes Mal neu, wenn sich das Basis-Template ändert:
Sie baut auf ihm auf. Was hier liegt, ist das Ergebnis — hier eine neue Fassung hineinlegen und
committen genügt.

Das Basis-Template liegt zusätzlich in QuartzHubs Repository (`Resources/templates/qc-basic.qtpl`),
für die Tests und für Entwicklungsbauten ohne Netz; beide Kopien bleiben gleich. Bis zum
11. November entstanden die Pakete über `npm run template:example` im QuartzControl-Repository; die
Anpassung an Quartz 5.1 war ein Skript über dem Paket von 1.3.0, das nur die oben genannten
Einträge und die Zeilenumbrüche der Beispielseiten änderte.

---

*English:* the template packages QuartzHub offers when creating a project, as QuartzControl did
before it. Public because the app has to read the file without credentials; it caches it for a
day.
