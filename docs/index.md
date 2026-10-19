# DragKnife – Anleitung

DragKnife ist ein Add-In für Autodesk Fusion, das den G-Code für **Portal-CNC-Fräsen mit Drag-Knife (Schleppmesser) als Werkzeug** nachbearbeitet. Du programmierst deine Kontur wie gewohnt als 2D-Contour in Fusion – DragKnife macht daraus Code, mit dem das Messer an Ecken sauber ausgerichtet wird.

## Was DragKnife für dich erledigt

Ein Schleppmesser dreht sich nicht von selbst auf die neue Schnittrichtung. Der Standard-G-Code aus Fusion weiß davon nichts, an Ecken reißt oder verrundet die Klinge. DragKnife ergänzt deshalb:

- **Swivel an Ecken:** Das Messer hebt an, richtet sich in die neue Richtung aus und taucht wieder ein.
- **Entry-Swivel am Kontureinstieg:** Ab der zweiten Kontur richtet DragKnife die Klinge vor dem Einstich aus. Vor dem ersten Schnitt richtest du sie selbst von Hand aus.
- **Overcut am Konturende:** Die Spindel fährt einen Blade offset weiter, damit die Klingenspitze den Endpunkt der Kontur erreicht.
- **Pro:** Die Klingenspitze folgt der programmierten Kontur exakt, auch auf Kurven. Dazu kommt eine Live-Vorschau des Werkzeugwegs.

## Was du brauchst

- Autodesk Fusion mit einer 2D-Contour-Operation (Linien und Bögen in der XY-Ebene)
- eine Portal-CNC mit Schleppmesser als Werkzeug
- den **Blade offset** deines Messers (Abstand von Klingenspitze zur Drehachse). Kennst du ihn nicht, ermittelst du ihn über die [Kalibrierung](aufgaben/kalibrieren.md).

## So läuft es ab

1. Kontur in Fusion als 2D-Contour programmieren
2. Werkzeug und Material in DragKnife wählen
3. G-Code mit DragKnife erzeugen und prüfen
4. auf der Maschine schneiden

Der Weg im Detail steht im [Quickstart](quickstart.md).

<div class="grid cards" markdown>

-   **Zum ersten Schnitt**

    ---

    Von der Installation bis zum fertigen Teil in wenigen Schritten.

    [:octicons-arrow-right-24: Quickstart](quickstart.md)

-   **Fusion richtig vorbereiten**

    ---

    Die häufigste Fehlerquelle liegt im Fusion-Setup.

    [:octicons-arrow-right-24: Vorbereitung](fusion-vorbereitung.md)

-   **Es klappt nicht?**

    ---

    Symptom, Ursache, Lösung.

    [:octicons-arrow-right-24: Fehlersuche](fehlersuche.md)

</div>

!!! info "Eco oder Pro?"
    Seiten und Abschnitte, die nur in **DragKnife Pro** vorhanden sind, tragen die Markierung *(Pro)*. Einen Überblick findest du unter [Eco und Pro](eco-pro.md).
