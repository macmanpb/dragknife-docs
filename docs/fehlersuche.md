# Fehlersuche

Suche dein Problem in der passenden Gruppe. Die meisten Fälle lassen sich mit einem Blick in die [Checkliste](fusion-vorbereitung.md) beheben.

## Beim Schneiden: Ecken und Einstiege

| Symptom | Mögliche Ursache | Lösung | Gilt für |
|---|---|---|---|
| Messer sitzt am Konturanfang neben dem Schnitt | Entry-Point liegt auf einer Ecke | Entry-Point auf eine gerade Strecke legen → [Vorbereitung](fusion-vorbereitung.md) | Eco + Pro |
| Erster Schnitt reißt oder weicht von der Kontur ab | Messer war am Start nicht in die erste Schnittrichtung gedreht | Messer vor dem Start **von Hand** ausrichten → [Vorbereitung](fusion-vorbereitung.md) | Eco + Pro |
| Ecken sind abgerundet, oder die Schnitte überlappen an der Ecke | **Blade offset** stimmt nicht | **Pro:** [Messer kalibrieren](aufgaben/kalibrieren.md). **Eco:** **Blade offset** im Dialog anpassen und neu testen | Eco + Pro |
| An der Ecke bleibt eine Lücke oder ein Überstand | **Blade offset** stimmt nicht | **Pro:** [Messer kalibrieren](aufgaben/kalibrieren.md). **Eco:** **Blade offset** im Dialog anpassen und neu testen | Eco + Pro |
| Sichtbarer Überschnitt an Ecken und Enden bei dickem Material | Schräg gestellte Klinge, hängt von der Gesamttiefe ab | Lässt sich nicht verringern, auch nicht mit mehreren Durchgängen → [Grenzen](drag-knife-grenzen.md) | Eco + Pro |
| Flache Ecken sind nicht scharf | Richtungswechsel liegt unter der **Tolerance**. Eco fügt dort nichts ein, Pro dreht im Material | **Tolerance** im Dialog senken → [Swivel-Move](aufgaben/ecken-konturen.md) | Eco + Pro |

## Beim Schneiden: Swivel und Tiefe

| Symptom | Mögliche Ursache | Lösung | Gilt für |
|---|---|---|---|
| Messer schleppt oder reißt am Drehpunkt | Material ist dicker als eingetragen, die Spitze steckt beim Schwenken zu tief | Stärke nachmessen. **Pro:** **Thick** und **Lift** in der [Bibliothek](aufgaben/bibliothek.md) anpassen. **Eco:** **Swivel lift height** im Dialog anpassen | Eco + Pro |
| Messer taucht nach dem Drehen versetzt wieder ein | Material ist dünner als eingetragen, die Klinge hebt ganz aus dem Material | Stärke nachmessen. **Pro:** **Thick** und **Lift** in der [Bibliothek](aufgaben/bibliothek.md) anpassen. **Eco:** **Swivel lift height** im Dialog anpassen | Eco + Pro |
| Messer schneidet nicht durch | Schnitttiefe zu flach, oder Z0 liegt nicht auf der Materialunterseite | **WCS auf die Unterseite des Modells** setzen, Tiefe prüfen → [Vorbereitung](fusion-vorbereitung.md) | Eco + Pro |

## Beim Schneiden: Kurven und Konturen

| Symptom | Mögliche Ursache | Lösung | Gilt für |
|---|---|---|---|
| Kurven weichen von der Kontur ab | Ohne **Full path compensation** schleppt die Spitze auf Kurven nach | **Pro:** **Full path compensation** einschalten. **Eco:** nicht möglich, die Funktion gibt es nur in Pro | Eco + Pro |
| Kurven aus Schrift oder Logos sind wellig | **Smooth spindle** ist aus | **Smooth spindle** einschalten | Pro |
| Echte Bögen und Geraden (Schilder, Rahmen) weichen leicht ab | **Smooth spindle** ist an | **Smooth spindle** ausschalten | Pro |
| Der Schnitt liegt seitlich versetzt zur Kontur | In Fusion ist eine Werkzeugkorrektur aktiv | **Compensation type** auf **Off**, **Compensation radius allowance** auf **0** → [Checkliste](fusion-vorbereitung.md) | Eco + Pro |
| Konturen werden in wechselnder Richtung oder in anderer Reihenfolge geschnitten | In Fusion sind **Both ways** an oder **Preserve order** aus | **Both ways** aus, **Preserve order** an, rote Pfeile in dieselbe Richtung → [Checkliste](fusion-vorbereitung.md) | Eco + Pro |
| Kurze gerade Strecken hinter einer Ecke fehlen | Eco lässt Strecken unter einem Blade offset aus | **Pro** mit **Full path compensation** fährt sie. Sonst Details größer planen → [Grenzen](drag-knife-grenzen.md) | Eco, Pro nur ohne Kompensierung |

## Beim Erzeugen der Datei

| Meldung oder Symptom | Ursache | Lösung | Gilt für |
|---|---|---|---|
| *„No active CAM data in this document!"* | Du bist nicht im Arbeitsbereich **Manufacture**, oder das Dokument hat keine CAM-Daten | In **Manufacture** wechseln und eine Operation anlegen → [Quickstart](quickstart.md) | Eco + Pro |
| Meldung zu einem Bogen **außerhalb der XY-Ebene** mit Zeilennummer | Vertikaler Lead-In oder Lead-Out in Fusion | **Lead-In (Entry)** und **Lead-Out (Exit)** auf dem Tab **Linking** ausschalten, Datei neu ausgeben → [Grenzen](drag-knife-grenzen.md) | Eco + Pro |
| **Swivel feedrate** ist ausgegraut | Es ist noch keine Datei gewählt, die Einheit kommt aus der Datei | Zuerst **Select file** klicken | Eco + Pro |
| Warnsymbol neben dem Dateinamen | Tiefstes Z liegt über Z0, Klingentiefe über **Max. depth**, oder mehrere Tiefenzustellungen | Mauszeiger auf das Symbol halten, dort steht der Grund → [Schnitttiefen-Hinweis](fusion-vorbereitung.md) | Pro |
| Es fehlen die Tabs **Tools**, **Materials** und **Calibration** oder die Vorschau | Du nutzt Eco | Diese Funktionen gibt es nur in Pro → [Eco und Pro](eco-pro.md) | Eco |
| Meldung, dass die Python-Version von Fusion nicht mehr passt | Fusion wurde aktualisiert und hat seine Python-Version gewechselt | Die aktuelle DragKnife-Version installieren | Eco + Pro |

## Bibliothek und Kalibrierung *(Pro)*

| Symptom | Ursache | Lösung | Gilt für |
|---|---|---|---|
| Neuer Eintrag erscheint nicht im Drop-down | Die Zeile wurde nicht abgeschlossen oder ein Pflichtfeld fehlt | Pflichtfelder füllen, Zeile mit dem **grünen Haken** abschließen → [Bibliothek](aufgaben/bibliothek.md) | Pro |
| Kalibrierung meldet *„r₀ − g would be ≤ 0"* | Bei **Cut crosses past the corner** ist **g** so groß wie **r₀** oder größer. Der Blade offset kann aber nicht null oder negativ sein | Siehe Kasten unter der Tabelle → [Kalibrieren](aufgaben/kalibrieren.md) | Pro |
| **Save to library** speichert nicht | **Name** oder **Max. depth** fehlt | Beide Felder ausfüllen | Pro |

!!! info "Kalibrierung meldet „r₀ − g would be ≤ 0""
    Die Meldung erscheint nur beim Fall **Cut crosses past the corner**, bei dem der Assistent **r = r₀ − g** rechnet. Das Ergebnis kann nie null oder negativ sein, ein Messer ohne Abstand zwischen Spitze und Drehachse gibt es nicht. Prüfe der Reihe nach:

    1. **Richtigen Fall gewählt?** Bei einer Lücke vor der Ecke gilt **Gap before the corner** (r = r₀ + g). Verwechselt man die beiden Fälle, passt die Rechnung nicht.
    2. **Richtig gemessen?** **g** ist nur der Abstand zwischen den beiden Linien an der Ecke, nicht die Länge der ganzen Kante und nicht beide Seiten zusammen. Weichen die Ecken voneinander ab, nimm den **Mittelwert**.
    3. **Einheit richtig?** **g** wird in der Einheit des Dokuments eingegeben. Ein Wert in Millimetern bei einem Zoll-Dokument (oder umgekehrt) ist um den Faktor 25,4 daneben.
    4. **r₀ stimmt mit dem Testschnitt überein?** Der Wert im Tab **Calibration** muss derselbe sein, mit dem du die Testdatei erzeugt hast. Hast du ihn danach geändert, passt die Messung nicht mehr.
    5. **r₀ viel zu groß geschätzt?** Dann ist **g** sehr groß, und die Rechnung wird ungenau. Erzeuge die Testdatei mit einem realistischen Schätzwert neu (zum Beispiel der Herstellerangabe), schneide sie und miss noch einmal.
