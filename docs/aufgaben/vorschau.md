# Vorschau nutzen *(Pro)*

Die Vorschau zeigt den Werkzeugweg als Grafik, bevor du etwas auf die Maschine schickst. Du siehst jede Bewegung, kannst sie abspielen und Zeile für Zeile durch den G-Code gehen. Dazu läuft eine Positionsanzeige (X/Y/Z/F) mit.

<figure markdown="span">
  ![Die Vorschau mit Werkzeugweg, Legende, G-Code und Positionsanzeige](../assets/img/vorschau-gesamt-light.png#only-light)
  ![Die Vorschau mit Werkzeugweg, Legende, G-Code und Positionsanzeige](../assets/img/vorschau-gesamt-dark.png#only-dark)
  <figcaption>Die Vorschau: oben der Werkzeugweg mit Legende, unten der G-Code und die Positionsanzeige</figcaption>
</figure>

## Vorschau öffnen

Es gibt zwei Wege:

- **Vor dem Erzeugen:** Im Tab **Options** lädst du mit **Select file** deine Fusion-Datei und aktivierst **Preview loaded file**. Die Vorschau zeigt dann die **Originaldatei**, also den Weg, den Fusion ausgegeben hat.
- **Nach dem Erzeugen:** Nach **OK** fragt DragKnife, ob du die erzeugte Datei in der Vorschau sehen willst (**Yes** = Vorschau, **No** = schließen). Dann siehst du die **`_dragknife`-Datei** mit allen Swivel-Moves.

!!! tip "Original und Ergebnis vergleichen"
    Öffne zuerst die Originaldatei und danach die erzeugte. So siehst du genau, was DragKnife an jeder Ecke eingefügt hat.

## Ansicht

Oben wählst du unter **View** die Darstellung:

| Ansicht | Beschreibung |
|---|---|
| **2D Top** | Draufsicht, ideal zum Prüfen von Konturen und Ecken |
| **2.5D** | Schräge Ansicht mit Höhenversatz |
| **3D Orbit** | Frei drehbare 3D-Ansicht |

<figure markdown="span">
  ![Die 3D-Ansicht der Vorschau](../assets/img/vorschau-3d-light.png#only-light)
  ![Die 3D-Ansicht der Vorschau](../assets/img/vorschau-3d-dark.png#only-dark)
  <figcaption>Dieselbe Datei in der Ansicht <strong>3D Orbit</strong></figcaption>
</figure>

**Fit** zeigt den ganzen Werkzeugweg, **Reset view** setzt die Ansicht zurück.

## Farben

Jede Bewegungsart hat ihre Farbe. Die Legende steht im Bild.

| Farbe | Bedeutung |
|---|---|
| <span class="dk-sw" style="background:var(--dk-rapid)"></span> **Rapid** | Eilgang, das Messer fährt ohne zu schneiden |
| <span class="dk-sw" style="background:var(--dk-pcut)"></span> **Cut** | Schnitt |
| <span class="dk-sw" style="background:var(--dk-plunge)"></span> **Plunge / Retract** | Eintauchen und Herausfahren |
| <span class="dk-sw" style="background:var(--dk-swivel)"></span> **Swivel / Lifted move** | Schwenken und Bewegungen mit angehobenem Messer |
| <span class="dk-sw" style="background:var(--dk-ramp)"></span> **Ramp** | Schräges Eintauchen |
| <span class="dk-sw" style="background:var(--dk-spindle)"></span> **Path compensation** | Der kompensierte Spindelweg (nur mit *Full path compensation*) |

## Abspielen

Mit **Play** (oder der **Leertaste**) läuft der Werkzeugweg als Animation ab. Das Messer wird dabei als kleines Werkzeugsymbol mit Schnittrichtung gezeigt.

- **Zum Anfang** und **Ans Ende** springen an den ersten bzw. letzten Bewegungsschritt (**Home** / **End**).
- Der Pfeil neben Play öffnet die **Geschwindigkeit**: 20 % bis 200 % der Maschinen-Feedrate.

## Anzeige-Einstellungen

Das Zahnrad öffnet die Einstellungen:

| Option | Wirkung |
|---|---|
| **Grid** | Raster ein/aus |
| **Origin** | Nullpunkt anzeigen |
| **Rapids** | Eilgänge anzeigen |
| **Cuts** | Schnitte anzeigen |
| **Direction arrows** | Pfeile für die Bewegungsrichtung |
| **Toolpath points** | Punkte auf dem Weg, ein Klick springt zur G-Code-Zeile |
| **Animate swivel** | Swivel-Schwenk beim Anspringen einer Zeile animieren |
| **Follow** | Die Ansicht folgt dem Werkzeug |
| **Path compensation** | Den kompensierten Spindelweg zeigen |

Deine Einstellungen werden gespeichert und beim nächsten Öffnen wiederhergestellt.

## G-Code und Positionsanzeige

Unter dem Bild steht der **G-Code**. Die aktuelle Zeile ist hervorgehoben, und das Werkzeugsymbol steht an der passenden Stelle im Bild.

- **Pfeiltasten** springen von einer Bewegungszeile zur nächsten. Kommentare und M-Codes werden übersprungen.
- Der **Kopieren**-Knopf legt den G-Code in die Zwischenablage.
- Mit der Leiste dazwischen änderst du die Höhe des G-Code-Bereichs, die Kopfzeile klappt ihn zu.
- Rechts daneben zeigt die **Positionsanzeige** **X, Y, Z** und **F** der aktuellen Zeile. **X** und **Y** sind die Spindelkoordinaten (also die Maschinenposition) und nicht die Klingenspitze. Bei Eilgängen steht bei **F** ein Strich.

## Info

Der Knopf **Info** zeigt eine Statistik zum Werkzeugweg: Anzahl und Art der Bewegungen, **Schnittlänge**, Weg der Eilgänge, die geschätzte **Zeit** und die Ausdehnung in X, Y und Z.

<figure markdown="span">
  ![Die Info-Karte der Vorschau](../assets/img/vorschau-info-light.png#only-light)
  ![Die Info-Karte der Vorschau](../assets/img/vorschau-info-dark.png#only-dark)
  <figcaption>Die Info-Karte mit Statistik zum Werkzeugweg</figcaption>
</figure>

!!! note "Die Zeit ist nur ein Schätzwert"
    Die Zeit richtet sich nach den Vorschüben im G-Code. Für Eilgänge wird das Dreifache des höchsten Schnittvorschubs angenommen. Die Maschine selbst kann abweichen.

## Bedienung auf einen Blick

| Eingabe | Wirkung |
|---|---|
| Ziehen, Mausrad (2D, 2.5D) | Verschieben, Zoomen |
| Ziehen, **Shift** + Ziehen, Mausrad (3D) | Drehen, Verschieben, Heranzoomen |
| Klick auf einen Punkt | Springt zur G-Code-Zeile (**Toolpath points** muss an sein) |
| **Pfeiltasten** | Durch die Bewegungszeilen steppen |
| **Home** / **End** | Erste / letzte Bewegungszeile |
| **Leertaste** | Play / Stop |

## Was du prüfen solltest

- Sitzt an jeder Ecke ein **Swivel** (orange)?
- Liegt der Einstieg wie geplant, nicht auf einer Ecke?
- Passt die **Z-Tiefe**? Der schmale Balken neben dem Bild zeigt sie.
- Verläuft der rote **Spindelweg** sinnvoll an Kurven entlang?
