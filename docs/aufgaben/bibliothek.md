# Werkzeuge und Materialien verwalten *(Pro)*

In zwei Bibliotheken legst du deine **Messer** und deine **Materialien** einmal an und wählst sie danach nur noch aus. Das spart das Eintippen und verhindert Zahlendreher bei Blade offset und Lift-Höhe.

<figure markdown="span">
  ![Der Tab Tools mit zwei Messern](../assets/img/bibliothek-tools-light.png#only-light)
  ![Der Tab Tools mit zwei Messern](../assets/img/bibliothek-tools-dark.png#only-dark)
  <figcaption>Der Tab <strong>Tools</strong></figcaption>
</figure>

<figure markdown="span">
  ![Der Tab Materials mit drei Materialien](../assets/img/bibliothek-materials-light.png#only-light)
  ![Der Tab Materials mit drei Materialien](../assets/img/bibliothek-materials-dark.png#only-dark)
  <figcaption>Der Tab <strong>Materials</strong></figcaption>
</figure>

## Die beiden Bibliotheken

| Tab | Felder | Wofür |
|---|---|---|
| **Tools** | **Name**, **Blade offset**, **Max. depth** | Dein Messer: Abstand Klingenspitze – Drehachse und maximale Schnitttiefe der Klinge |
| **Materials** | **Name**, **Lift**, **Thick**, **URL**, **Notes** | Dein Material: Swivel-Lift-Höhe, Materialstärke, Link zum Hersteller und Notizen |

Alle Zahlenfelder (mit `*` markiert) sind Pflicht, ebenso der **Name**. Du kannst Werte wie in Fusion eingeben (zum Beispiel `1,5`, `3/8` oder `2"`). Die Anzeige folgt der Einheit deines Fusion-Dokuments.

!!! warning "Materialstärke und Lift-Höhe müssen zum echten Material passen"
    DragKnife kennt nur die Werte, die du einträgst. Es erkennt nicht, welches Material tatsächlich auf der Maschine liegt.

    - **Material dicker als eingetragen:** Der Hebepunkt liegt zu tief, die Klingenspitze steckt beim Schwenken **zu tief im Material**. Die Klinge schleppt oder reißt am Drehpunkt, statt sich frei zu drehen.
    - **Material dünner als eingetragen:** Die Klinge hebt aus dem Material heraus und taucht nach dem Drehen **versetzt** wieder ein.

    **Miss die Materialstärke deshalb nach** und trage den gemessenen Wert in **Thick** ein. Lege für jede Stärke und jede Charge mit abweichender Dicke eine **eigene Materialzeile** an (zum Beispiel „Karton 3,0 mm" und „Karton 3,5 mm"). Die **Lift**-Höhe stellst du pro Zeile passend ein.

## Einträge anlegen und bearbeiten

1. Klicke unter der Tabelle auf **+**. Es erscheint eine neue Zeile mit Eingabefeldern.
2. Fülle die Pflichtfelder aus. Fehlt eines, erscheint der Hinweis *„Fill the required fields (\*) to finish the row — or delete it."*, und das Feld wird rot markiert.
3. Schließe die Zeile mit dem **grünen Haken** oder mit **Enter** ab. Der Stift in einer fertigen Zeile öffnet sie wieder zum Bearbeiten, der Mülleimer löscht sie.

Ein Klick auf eine Spaltenüberschrift sortiert die Tabelle. Die Sortierung bleibt erhalten.

## Einträge verwenden

Es gibt zwei Wege, einen Eintrag in die Einstellungen zu übernehmen:

- Im Tab **Options** im Drop-down **Tool** bzw. **Material** auswählen.
- In der Bibliothek auf die Zeile **doppelklicken**. Danach wechselt der Dialog zu **Options**.

Dabei werden die Werte in die Felder des Tabs **Options** geschrieben, und zwar so:

| Auswahl | Wird übernommen in | Zusätzlich |
|---|---|---|
| **Tool** | **Blade offset** | **Max. depth** wird für den [Schnitttiefen-Hinweis](../fusion-vorbereitung.md) benutzt |
| **Material** | **Swivel lift height** | **Thick** wird für den Schnitttiefen-Hinweis benutzt |

Die Felder in **Options** bleiben danach **überschreibbar**: Du kannst den Wert für einen einzelnen Auftrag anpassen, ohne die Bibliothek zu ändern.

!!! note "Tolerance und Swivel feedrate gehören nicht zur Bibliothek"
    **Tolerance** und **Swivel feedrate (F)** sind Prozess-Einstellungen und werden direkt im Tab **Options** gepflegt.

## Hersteller-Link

Steht in **URL** ein Link, öffnet ein Klick darauf die Seite im Standard-Browser. So findest du Datenblatt oder Bezugsquelle des Materials schnell wieder.

## Wo die Daten liegen

Die Bibliothek wird in der Datei `DragKnife_library.json` im Benutzerverzeichnis gespeichert, **außerhalb** des Add-In-Ordners:

| System | Ordner |
|---|---|
| macOS | `~/Library/Application Support/DragKnife` |
| Windows | `%APPDATA%\DragKnife` |

Ein Update des Add-Ins löscht deine Einträge deshalb nicht. Für ein **Backup** oder den Umzug auf einen anderen Rechner kopierst du diese Datei.

!!! tip "Messer kalibrieren"
    Der [Kalibrier-Assistent](kalibrieren.md) speichert das ermittelte Messer direkt als neuen Eintrag in der Bibliothek **Tools**.
