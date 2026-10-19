# Messer kalibrieren *(Pro)*

Der **Blade offset** ist der Abstand von der Klingenspitze zur Drehachse. Er ist der wichtigste Wert für saubere Ecken. Der Kalibrier-Assistent im Tab **Calibration** ermittelt ihn aus einem Testquadrat: Du schneidest es mit deinem geschätzten Wert, misst die Abweichung an einer Ecke und bekommst den genauen Wert, direkt in die Tools-Bibliothek gespeichert.

!!! note "Was du brauchst"
    - Einen **Schätzwert** für den Blade offset (Herstellerangabe oder grob gemessen). Er heißt im Assistenten **r₀**.
    - Etwas Restmaterial für den Testschnitt und eine Möglichkeit, eine Lücke oder einen Überstand an einer Ecke zu messen.

<figure markdown="span">
  ![Der Tab Calibration mit den drei Schritten](../assets/img/kalibrierung-tab-light.png#only-light)
  ![Der Tab Calibration mit den drei Schritten](../assets/img/kalibrierung-tab-dark.png#only-dark)
  <figcaption>Der Tab <strong>Calibration</strong></figcaption>
</figure>

## 1. Testquadrat erzeugen

1. Öffne im Dialog den Tab **Calibration**.
2. Trage die **Square size** ein (10 bis 500 mm) und klicke **Create test sketch**.
3. Der Dialog schließt sich dabei, das Quadrat erscheint als Skizze im Design. Das ist nötig, weil Fusion Änderungen am Modell nur außerhalb eines offenen Dialogs übernimmt.
4. Lege auf der Skizze wie gewohnt eine **2D-Contour** an und gib den G-Code mit **dem Post deiner Maschine** aus.

!!! warning "Entry-Point mittig auf eine Kante"
    Lege den Einstiegspunkt auf die **Mitte einer Kante**, nicht auf eine Ecke. Sonst verfälscht der Einstich die Messung an dieser Ecke. → [In Fusion vorbereiten](../fusion-vorbereitung.md)

5. Öffne DragKnife wieder. Dein eingegebener Wert r₀ ist gespeichert und wird wiederhergestellt.

## 2. Quadrat schneiden

1. Trage im Tab **Calibration** deinen Schätzwert als **Blade offset r₀** ein. Er wird mit dem **Blade offset** im Tab **Options** abgeglichen.
2. Lade die ausgegebene Datei im Tab **Options** mit **Select file**, erzeuge die `_dragknife`-Datei und schneide das Quadrat auf der Maschine.

!!! warning "Die Testdatei muss exakt mit diesem r₀ erzeugt werden"
    Der Wert in **Blade offset** (Options) und in **r₀** (Calibration) muss bei der Erzeugung der Testdatei derselbe sein. Ändere ihn nicht zwischen Erzeugen und Messen.

!!! warning "Messer von Hand ausrichten"
    Auch beim Testschnitt musst du das Messer vor dem Start **selbst** in die erste Schnittrichtung drehen.

## 3. Ecke vergleichen, messen, speichern

Schau dir eine Ecke des geschnittenen Quadrats an. Gestrichelt ist die gewollte Kontur, grün der tatsächliche Schnitt. Es gibt drei Fälle:

<div class="dk-figures" markdown="0">
<figure>
<svg viewBox="0 0 177 177" preserveAspectRatio="xMidYMid meet" role="img">
<path d="M0 130 L109.2 130 L109.2 0" fill="none" stroke="var(--dk-dim)" stroke-width="1" stroke-dasharray="5 4" />
<circle cx="109.2" cy="130" r="2.5" fill="none" stroke="var(--dk-dim)" stroke-width="1" />
<circle cx="109.2" cy="130" r="2" fill="var(--dk-scratch)" opacity="0.85" />
<path d="M0 130 L109.2 130 M109.2 130 L109.2 0" fill="none" stroke="var(--dk-cut)" stroke-width="2" stroke-linecap="round" />
</svg>
<figcaption>Ecken treffen sich exakt: der Offset stimmt</figcaption>
</figure>
<figure>
<svg viewBox="0 0 177 177" preserveAspectRatio="xMidYMid meet" role="img">
<defs>
<marker id="arB" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
<path d="M2 1L8 5L2 9" fill="none" stroke="var(--dk-dim)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
</marker>
</defs>
<path d="M0 130 L109.2 130 L109.2 0" fill="none" stroke="var(--dk-dim)" stroke-width="1" stroke-dasharray="5 4" />
<circle cx="109.2" cy="130" r="2.5" fill="none" stroke="var(--dk-dim)" stroke-width="1" />
<path d="M83.2 130 L81.8 130.2 L80 130.7 L78.3 131.4 L76.3 132.3 L74.9 133.1 L73.3 134 L71.6 135.1 L70.6 135.7" fill="none" stroke="var(--dk-scratch)" stroke-width="1.2" stroke-dasharray="2 3" opacity="0.85" />
<path d="M0 130 L83.2 130" fill="none" stroke="var(--dk-cut)" stroke-width="2" stroke-linecap="round" />
<path d="M70.6 135.7 L74.4 132.7 L77.7 129.5 L80.2 126.4 L82.7 123.1 L85.1 119.4 L87.8 114.4 L90.8 108 L93.9 100.1 L97.1 89.4 L100.7 73.3 L104.4 46.6 L107.4 0" fill="none" stroke="var(--dk-cut)" stroke-width="2" stroke-linecap="round" />
<line x1="83.2" y1="136" x2="83.2" y2="151" stroke="var(--dk-dim)" stroke-width="0.75" />
<line x1="109.2" y1="136" x2="109.2" y2="151" stroke="var(--dk-dim)" stroke-width="0.75" />
<line x1="85.2" y1="147" x2="107.2" y2="147" stroke="var(--dk-dim)" stroke-width="1" marker-start="url(#arB)" marker-end="url(#arB)" />
<text x="96.2" y="166" text-anchor="middle" font-size="12" fill="currentColor">g</text>
</svg>
<figcaption>Lücke vor der Ecke: r = r₀ + g</figcaption>
</figure>
<figure>
<svg viewBox="0 0 177 177" preserveAspectRatio="xMidYMid meet" role="img">
<defs>
<marker id="arC" viewBox="0 0 10 10" refX="8" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
<path d="M2 1L8 5L2 9" fill="none" stroke="var(--dk-dim)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" />
</marker>
</defs>
<path d="M0 130 L109.2 130 L109.2 0" fill="none" stroke="var(--dk-dim)" stroke-width="1" stroke-dasharray="5 4" />
<circle cx="109.2" cy="130" r="2.5" fill="none" stroke="var(--dk-dim)" stroke-width="1" />
<path d="M135.2 130 L136.4 129.7 L137.6 129.1 L138.9 128.1 L139.9 127.1 L140.9 125.9 L141.9 124.5 L142.8 122.8 L143.5 120.9 L144.1 118.8 L144.5 116.6 L144.7 114.1 L144.7 111.6 L144.4 108.9 L143.8 106.2 L143 103.5 L141.2 99.4 L138.7 95.4 L137.8 94.2" fill="none" stroke="var(--dk-scratch)" stroke-width="1.2" stroke-dasharray="2 3" opacity="0.85" />
<path d="M0 130 L135.2 130" fill="none" stroke="var(--dk-cut)" stroke-width="2" stroke-linecap="round" />
<path d="M137.8 94.2 L135.4 90.8 L133 87.1 L130.3 82.1 L127.3 75.6 L124.3 67.7 L121.1 57 L117.6 40.8 L113.9 14.1 L112.7 0" fill="none" stroke="var(--dk-cut)" stroke-width="2" stroke-linecap="round" />
<line x1="109.2" y1="136" x2="109.2" y2="151" stroke="var(--dk-dim)" stroke-width="0.75" />
<line x1="135.2" y1="136" x2="135.2" y2="151" stroke="var(--dk-dim)" stroke-width="0.75" />
<line x1="111.2" y1="147" x2="133.2" y2="147" stroke="var(--dk-dim)" stroke-width="1" marker-start="url(#arC)" marker-end="url(#arC)" />
<text x="122.2" y="166" text-anchor="middle" font-size="12" fill="currentColor">g</text>
</svg>
<figcaption>Schnitt kreuzt über die Ecke hinaus: r = r₀ − g</figcaption>
</figure>
</div>

| Beobachtung | Auswahl im Assistenten | Formel |
|---|---|---|
| Ecken treffen sich exakt | **Corners meet exactly** | r = r₀ |
| Lücke vor der Ecke | **Gap before the corner** | r = r₀ + g |
| Schnitt kreuzt über die Ecke hinaus | **Cut crosses past the corner** | r = r₀ − g |

1. Wähle den passenden Fall.
2. Miss die Abweichung **g** an der Ecke und trage sie bei **Measured g** ein. Weichen die Ecken leicht voneinander ab, nimm den **Mittelwert**.
3. Der Assistent zeigt den **tatsächlichen Blade offset r** an.
4. Vergib einen Namen bei **Save as tool** (Standard „Blade (calibrated)") und trage die **Max. depth** deiner Klinge ein, also die maximale Schnitttiefe.
5. Klicke **Save to library**. Das Messer liegt jetzt in der Bibliothek **Tools**.
6. Wähle es im Tab **Options** im Drop-down **Tool** aus. Sein Blade offset ist damit eingetragen.

!!! tip "Genauer wird es mit einem zweiten Durchlauf"
    Schneide das Quadrat mit dem neuen Wert noch einmal. Treffen sich die Ecken jetzt exakt, ist das Messer richtig kalibriert.
