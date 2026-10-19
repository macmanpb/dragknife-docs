# Eco und Pro

DragKnife gibt es in zwei Ausführungen. **Pro enthält alles aus Eco** und ergänzt Funktionen für genauere Schnitte, eine Vorschau und eine Verwaltung deiner Messer und Materialien.

## Auf einen Blick

| Funktion | Eco | Pro |
|---|:-:|:-:|
| **Swivel** an Richtungswechseln | ✓ | ✓ |
| **Auto align** am Kontureinstieg ab der zweiten Kontur | ✓ | ✓ |
| **Overcut** am Konturende | ✓ | ✓ (in der Kompensierung enthalten) |
| Einstellungen **Blade offset**, **Swivel lift height**, **Tolerance**, **Swivel feedrate** | ✓ | ✓ |
| **Full path compensation**: Die Klingenspitze folgt der Kontur auch auf Kurven exakt | – | ✓ |
| Drehen im Material bei flachen Ecken (mit Full path compensation) | – | ✓ |
| **Smooth spindle**: Glättung von Kurven aus vielen kurzen Strecken | – | ✓ |
| **Vorschau** mit Wiedergabe, Positionsanzeige und Statistik | – | ✓ |
| **Tools**- und **Materials**-Bibliothek | – | ✓ |
| **Calibration**: Kalibrier-Assistent für den Blade offset | – | ✓ |
| **Schnitttiefen-Hinweis** (Warnsymbol neben dem Dateinamen) | – | ✓ |

Die beiden Dialoge im Vergleich:

<div class="dk-figures" markdown="0">
<figure>
<img alt="Der Dialog von DragKnife Eco" src="../assets/img/dialog-options-eco.png">
<figcaption>Eco: nur der Tab <strong>Options</strong></figcaption>
</figure>
<figure>
<img alt="Der Dialog von DragKnife Pro" src="../assets/img/dialog-options-pro.png">
<figcaption>Pro: zusätzlich <strong>Tools</strong>, <strong>Materials</strong>, <strong>Calibration</strong></figcaption>
</figure>
</div>

## Was du in Eco bekommst

Der Dialog hat einen Tab **Options**. Dort lädst du die Datei mit **Select file**, trägst die Werte ein und erzeugst die `_dragknife`-Datei. Danach zeigt DragKnife den Pfad der fertigen Datei an.

Eco folgt dem Standard-Prinzip: Die **Spindel** folgt der Kontur, die Klingenspitze schleppt dahinter. Swivel und Overcut sorgen dafür, dass Ecken und Konturenden sauber werden. Auf Kurven weicht die Spitze dabei leicht von der Kontur ab.

## Was Pro dazugibt

- **Genauere Kurven:** Mit **Full path compensation** (standardmäßig an) wird der Spindelweg so vorausversetzt, dass die Klingenspitze die Kontur exakt abfährt. **Smooth spindle** glättet dabei Kurven, die Fusion in viele kurze Strecken zerlegt hat. → [Quickstart](quickstart.md)
- **Vorschau:** Du siehst den Werkzeugweg vor dem Schneiden, spielst ihn ab und gehst Zeile für Zeile durch den G-Code. → [Vorschau](aufgaben/vorschau.md)
- **Bibliotheken:** Messer und Materialien einmal anlegen, danach nur noch auswählen. → [Bibliothek](aufgaben/bibliothek.md)
- **Kalibrierung:** Den Blade offset aus einem Testquadrat ermitteln und direkt als Messer speichern. → [Messer kalibrieren](aufgaben/kalibrieren.md)
- **Schnitttiefen-Hinweis:** Das Warnsymbol macht auf zu flache Schnitte, zu tiefe Klingentiefen und mehrere Tiefenzustellungen aufmerksam. → [In Fusion vorbereiten](fusion-vorbereitung.md)
