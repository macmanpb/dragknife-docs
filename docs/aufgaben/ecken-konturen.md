# Ecken: der Swivel-Move

Ein Schleppmesser richtet sich nicht von selbst auf die neue Schnittrichtung aus. Die Klingenspitze liegt um den **Blade offset** hinter der Drehachse (der Spindel). Fährt die Maschine einfach um die Ecke, wird die Klinge quer durch das Material geschleift und reißt oder verrundet die Ecke.

Der **Swivel-Move** löst das: Die Maschine dreht das Messer **auf der Stelle** um die Klingenspitze. Die Spitze bleibt dabei am Eckpunkt, nur die Spindel schwenkt auf einem Bogen mit dem Radius des Blade offset in die neue Richtung.

!!! warning "Wichtig: Die Startausrichtung machst du selbst"
    Die **initiale Ausrichtung des Messers** muss **der Anwender vor dem Start von Hand vornehmen**: Dreh die Klinge am Startpunkt so, dass sie in die Richtung des ersten Schnitts zeigt. DragKnife kann nur Richtungswechsel **innerhalb** der Kontur ausrichten, nicht die Ausgangslage des Messers vor dem ersten Schnitt.

<figure markdown="span">
<svg viewBox="0 0 340 210" role="img" aria-label="Swivel-Move: die Spindel schwenkt auf einem Bogen um die Klingenspitze am Eckpunkt" style="max-width:420px;width:100%;height:auto;color:var(--md-default-fg-color)">
  <!-- Kontur -->
  <polyline points="20,170 110,170 190,47" fill="none" stroke="currentColor" stroke-width="2" opacity=".5"/>
  <!-- Schnittrichtung -->
  <polygon points="78,170 66,164 66,176" fill="currentColor"/>
  <polygon points="190,47 187.7,59.8 179.3,54.4" fill="currentColor"/>
  <text x="48" y="156" font-size="12" fill="currentColor" text-anchor="middle">Schnittrichtung</text>
  <text x="198" y="44" font-size="12" fill="currentColor">neue Schnittrichtung</text>
  <!-- Messer vor dem Swivel -->
  <line x1="110" y1="170" x2="200" y2="170" stroke="currentColor" stroke-width="2" stroke-dasharray="5 4" opacity=".6"/>
  <circle cx="200" cy="170" r="7" fill="none" stroke="currentColor" stroke-width="2" opacity=".6"/>
  <!-- Swivel-Bogen -->
  <path d="M 200 170 A 90 90 0 0 0 155 92" fill="none" stroke="var(--dk-arc)" stroke-width="3"/>
  <polygon points="155,92 148,104 162,100" fill="var(--dk-arc)"/>
  <!-- Messer nach dem Swivel -->
  <line x1="110" y1="170" x2="155" y2="92" stroke="currentColor" stroke-width="2.5"/>
  <circle cx="155" cy="92" r="7" fill="currentColor"/>
  <!-- Klingenspitze -->
  <circle cx="110" cy="170" r="5" fill="var(--md-primary-fg-color)"/>
  <text x="110" y="196" font-size="12" fill="currentColor" text-anchor="middle">Klingenspitze = Drehpunkt</text>
  <text x="210" y="160" font-size="12" fill="currentColor">Spindel vorher</text>
  <text x="168" y="86" font-size="12" fill="currentColor">Spindel nachher</text>
  <text x="196" y="118" font-size="12" fill="var(--dk-arc)">Swivel-Bogen</text>
  <text x="196" y="132" font-size="11" fill="var(--dk-arc)">(Radius = Blade offset)</text>
</svg>
<figcaption>Die Spindel schwenkt um die feststehende Klingenspitze.</figcaption>
</figure>

## Der Ablauf Schritt für Schritt

<div class="dk-figures dk-steps" markdown="0">
<figure>
<svg viewBox="0 0 160 250" role="img" aria-label="Swivel Schritt 1: Draufsicht: Spitze erreicht den Eckpunkt. Seitenansicht: Messer schneidet in voller Tiefe.">
<polyline points="10,100 60,100 90,48" fill="none" stroke="var(--dk-dim)" stroke-width="1.5" stroke-dasharray="2 4"/>
<line x1="10" y1="100" x2="60" y2="100" stroke="var(--dk-cut)" stroke-width="2.5" stroke-linecap="round"/>
<line x1="60" y1="100" x2="96" y2="100" stroke="currentColor" stroke-width="2.5"/>
<circle cx="96" cy="100" r="6" fill="none" stroke="currentColor" stroke-width="2"/>
<circle cx="60" cy="100" r="3.5" fill="var(--dk-scratch)"/>
<line x1="8" y1="124" x2="152" y2="124" stroke="var(--dk-dim)" stroke-width=".75" opacity=".5"/>
<rect x="15" y="226" width="130" height="12" fill="var(--dk-cut)" opacity=".18"/>
<line x1="8" y1="238" x2="152" y2="238" stroke="currentColor" stroke-width="3"/>
<g transform="translate(30.5,138) scale(0.45)">
<rect x="100" y="8" width="20" height="50" fill="var(--dk-panel)" stroke="currentColor" stroke-width="1.5" vector-effect="non-scaling-stroke"/>
<rect x="88" y="58" width="44" height="48" rx="5" fill="var(--dk-panel)" stroke="currentColor" stroke-width="1.5" vector-effect="non-scaling-stroke"/>
<line x1="88" y1="66" x2="132" y2="66" stroke="currentColor" stroke-width="1" vector-effect="non-scaling-stroke"/>
<rect x="76" y="106" width="70" height="40" rx="4" fill="var(--dk-panel)" stroke="currentColor" stroke-width="1.5" vector-effect="non-scaling-stroke"/>
<polygon points="90,220 90,179 112,154 149,153" fill="currentColor" fill-opacity=".45" stroke="currentColor" stroke-width="1.2" stroke-linejoin="round" vector-effect="non-scaling-stroke"/>
<rect x="99" y="146" width="21" height="35" rx="2" fill="var(--dk-panel)" stroke="currentColor" stroke-width="1.5" vector-effect="non-scaling-stroke"/>
<circle cx="90" cy="219" r="5" fill="var(--dk-scratch)"/>
</g>
<line x1="80" y1="130" x2="80" y2="248" stroke="var(--dk-dim)" stroke-width="1" stroke-dasharray="5 4"/>
</svg>
<figcaption><strong>1 · Vorfahren</strong></figcaption>
</figure>
<figure>
<svg viewBox="0 0 160 250" role="img" aria-label="Swivel Schritt 2: Das Messer hebt auf die Lift-Höhe. Die Spitze steckt noch leicht im Material.">
<polyline points="10,100 60,100 90,48" fill="none" stroke="var(--dk-dim)" stroke-width="1.5" stroke-dasharray="2 4"/>
<line x1="10" y1="100" x2="60" y2="100" stroke="var(--dk-cut)" stroke-width="2.5" stroke-linecap="round"/>
<line x1="60" y1="100" x2="96" y2="100" stroke="currentColor" stroke-width="2.5"/>
<circle cx="96" cy="100" r="6" fill="none" stroke="currentColor" stroke-width="2"/>
<circle cx="60" cy="100" r="3.5" fill="var(--dk-scratch)"/>
<line x1="8" y1="124" x2="152" y2="124" stroke="var(--dk-dim)" stroke-width=".75" opacity=".5"/>
<rect x="15" y="226" width="130" height="12" fill="var(--dk-cut)" opacity=".18"/>
<line x1="8" y1="238" x2="152" y2="238" stroke="currentColor" stroke-width="3"/>
<g transform="translate(30.5,130) scale(0.45)">
<rect x="100" y="8" width="20" height="50" fill="var(--dk-panel)" stroke="currentColor" stroke-width="1.5" vector-effect="non-scaling-stroke"/>
<rect x="88" y="58" width="44" height="48" rx="5" fill="var(--dk-panel)" stroke="currentColor" stroke-width="1.5" vector-effect="non-scaling-stroke"/>
<line x1="88" y1="66" x2="132" y2="66" stroke="currentColor" stroke-width="1" vector-effect="non-scaling-stroke"/>
<rect x="76" y="106" width="70" height="40" rx="4" fill="var(--dk-panel)" stroke="currentColor" stroke-width="1.5" vector-effect="non-scaling-stroke"/>
<polygon points="90,220 90,179 112,154 149,153" fill="currentColor" fill-opacity=".45" stroke="currentColor" stroke-width="1.2" stroke-linejoin="round" vector-effect="non-scaling-stroke"/>
<rect x="99" y="146" width="21" height="35" rx="2" fill="var(--dk-panel)" stroke="currentColor" stroke-width="1.5" vector-effect="non-scaling-stroke"/>
<circle cx="90" cy="219" r="5" fill="var(--dk-scratch)"/>
</g>
<line x1="80" y1="130" x2="80" y2="248" stroke="var(--dk-dim)" stroke-width="1" stroke-dasharray="5 4"/>
<line x1="136" y1="214" x2="136" y2="190" stroke="var(--dk-arc)" stroke-width="2.5"/>
<polygon points="136,182 130,194 142,194" fill="var(--dk-arc)"/>
</svg>
<figcaption><strong>2 · Anheben</strong></figcaption>
</figure>
<figure>
<svg viewBox="0 0 160 250" role="img" aria-label="Swivel Schritt 3: Die Spindel schwenkt auf einem Bogen um die feststehende Spitze.">
<polyline points="10,100 60,100 90,48" fill="none" stroke="var(--dk-dim)" stroke-width="1.5" stroke-dasharray="2 4"/>
<line x1="10" y1="100" x2="60" y2="100" stroke="var(--dk-cut)" stroke-width="2.5" stroke-linecap="round"/>
<circle cx="96" cy="100" r="6" fill="none" stroke="currentColor" stroke-width="1.5" opacity=".4"/>
<path d="M 96 100 A 36 36 0 0 0 78 68.8" fill="none" stroke="var(--dk-arc)" stroke-width="2.5"/>
<polygon points="78,68.8 79,80.8 88,76.8" fill="var(--dk-arc)"/>
<line x1="60" y1="100" x2="78" y2="68.8" stroke="currentColor" stroke-width="2.5"/>
<circle cx="78" cy="68.8" r="6" fill="none" stroke="currentColor" stroke-width="2"/>
<circle cx="60" cy="100" r="3.5" fill="var(--dk-scratch)"/>
<line x1="8" y1="124" x2="152" y2="124" stroke="var(--dk-dim)" stroke-width=".75" opacity=".5"/>
<rect x="15" y="226" width="130" height="12" fill="var(--dk-cut)" opacity=".18"/>
<line x1="8" y1="238" x2="152" y2="238" stroke="currentColor" stroke-width="3"/>
<g transform="translate(30.5,130) scale(0.45)">
<rect x="100" y="8" width="20" height="50" fill="var(--dk-panel)" stroke="currentColor" stroke-width="1.5" vector-effect="non-scaling-stroke"/>
<rect x="88" y="58" width="44" height="48" rx="5" fill="var(--dk-panel)" stroke="currentColor" stroke-width="1.5" vector-effect="non-scaling-stroke"/>
<line x1="88" y1="66" x2="132" y2="66" stroke="currentColor" stroke-width="1" vector-effect="non-scaling-stroke"/>
<rect x="76" y="106" width="70" height="40" rx="4" fill="var(--dk-panel)" stroke="currentColor" stroke-width="1.5" vector-effect="non-scaling-stroke"/>
<polygon points="90,220 90,179 112,154 149,153" fill="currentColor" fill-opacity=".45" stroke="currentColor" stroke-width="1.2" stroke-linejoin="round" vector-effect="non-scaling-stroke"/>
<rect x="99" y="146" width="21" height="35" rx="2" fill="var(--dk-panel)" stroke="currentColor" stroke-width="1.5" vector-effect="non-scaling-stroke"/>
<circle cx="90" cy="219" r="5" fill="var(--dk-scratch)"/>
</g>
<line x1="80" y1="130" x2="80" y2="248" stroke="var(--dk-dim)" stroke-width="1" stroke-dasharray="5 4"/>
</svg>
<figcaption><strong>3 · Ausrichten</strong></figcaption>
</figure>
<figure>
<svg viewBox="0 0 160 250" role="img" aria-label="Swivel Schritt 4: Das Messer taucht wieder ein und schneidet in der neuen Richtung weiter.">
<polyline points="10,100 60,100 90,48" fill="none" stroke="var(--dk-dim)" stroke-width="1.5" stroke-dasharray="2 4"/>
<line x1="10" y1="100" x2="60" y2="100" stroke="var(--dk-cut)" stroke-width="2.5" stroke-linecap="round"/>
<line x1="60" y1="100" x2="78" y2="68.8" stroke="currentColor" stroke-width="2.5"/>
<circle cx="78" cy="68.8" r="6" fill="none" stroke="currentColor" stroke-width="2"/>
<circle cx="60" cy="100" r="3.5" fill="var(--dk-scratch)"/>
<polygon points="90,48 89,59 80,54" fill="currentColor" opacity=".6"/>
<line x1="8" y1="124" x2="152" y2="124" stroke="var(--dk-dim)" stroke-width=".75" opacity=".5"/>
<rect x="15" y="226" width="130" height="12" fill="var(--dk-cut)" opacity=".18"/>
<line x1="8" y1="238" x2="152" y2="238" stroke="currentColor" stroke-width="3"/>
<g transform="translate(30.5,138) scale(0.45)">
<rect x="100" y="8" width="20" height="50" fill="var(--dk-panel)" stroke="currentColor" stroke-width="1.5" vector-effect="non-scaling-stroke"/>
<rect x="88" y="58" width="44" height="48" rx="5" fill="var(--dk-panel)" stroke="currentColor" stroke-width="1.5" vector-effect="non-scaling-stroke"/>
<line x1="88" y1="66" x2="132" y2="66" stroke="currentColor" stroke-width="1" vector-effect="non-scaling-stroke"/>
<rect x="76" y="106" width="70" height="40" rx="4" fill="var(--dk-panel)" stroke="currentColor" stroke-width="1.5" vector-effect="non-scaling-stroke"/>
<polygon points="90,220 90,179 112,154 149,153" fill="currentColor" fill-opacity=".45" stroke="currentColor" stroke-width="1.2" stroke-linejoin="round" vector-effect="non-scaling-stroke"/>
<rect x="99" y="146" width="21" height="35" rx="2" fill="var(--dk-panel)" stroke="currentColor" stroke-width="1.5" vector-effect="non-scaling-stroke"/>
<circle cx="90" cy="219" r="5" fill="var(--dk-scratch)"/>
</g>
<line x1="80" y1="130" x2="80" y2="248" stroke="var(--dk-dim)" stroke-width="1" stroke-dasharray="5 4"/>
<line x1="136" y1="190" x2="136" y2="214" stroke="var(--dk-arc)" stroke-width="2.5"/>
<polygon points="136,222 130,210 142,210" fill="var(--dk-arc)"/>
</svg>
<figcaption><strong>4 · Eintauchen</strong></figcaption>
</figure>
</div>

<p class="dk-note">Jedes Bild zeigt oben die Draufsicht und unten die Seitenansicht.</p>

1. **Bis zum Drehpunkt vorfahren.** Das Messer schneidet in Schnitttiefe weiter, bis die **Klingenspitze exakt auf dem Eckpunkt** steht. Vorschub: Schnitt-Vorschub (Cut feedrate).
2. **Anheben.** Die Klinge fährt auf die **Lift**-Höhe: so weit, dass sie sich ohne Widerstand drehen kann, aber nicht weiter. **Die Klingenspitze bleibt dabei noch leicht im Material**, denn nur so bleibt sie am Eckpunkt stehen und der Schnitt setzt dort wieder sauber an. Hebt die Klinge ganz aus dem Material, kann die Spitze beim Drehen versetzt wieder eintauchen. Den Wert legst du pro Material fest (Bibliothek *Materials*).
3. **Ausrichten.** Die Spindel fährt einen Kreisbogen (G2/G3) um die Spitze, bis das Messer in der neuen Schnittrichtung zeigt. Vorschub: Swivel-Vorschub.
4. **Eintauchen.** Die Klinge fährt zurück auf Schnitttiefe, der Schnitt geht in der neuen Richtung weiter.

!!! tip "Warum bleibt die Ecke scharf?"
    Die Spitze wandert beim Drehen nicht. Sie sticht an der Stelle, an der die Kontur abknickt, wieder ein. Deshalb entsteht eine echte Ecke und kein Radius.

## Flache Ecken: Drehen im Material

Die **Toleranz** (Option *Tolerance* im Dialog, Standard 20°) legt fest, ab welchem Knickwinkel ein Swivel eingefügt wird. Darunter gilt das Messer als ausgerichtet.

- **Eco:** Bei Winkeln bis zur Toleranz wird nichts eingefügt, das Messer fährt einfach durch.
- **Pro (mit voller Pfad-Kompensierung):** Bei Winkeln zwischen 0,5° und der Toleranz dreht das Messer **im Material** auf einem kleinen Bogen um den Eckpunkt, ohne Anheben und Eintauchen und mit Schnitt-Vorschub. Darunter (unter 0,5°) wird nichts eingefügt.

## Kontureinstieg und -ende

- **Entry-Swivel:** Ab der **zweiten** Kontur vergleicht DragKnife die Messerrichtung des letzten Schnitts mit der neuen Schnittrichtung und fügt bei Bedarf einen Swivel ein, bevor das Messer eintaucht (Option *Auto align knife after initial entry*). Vor dem allerersten Schnitt gibt es keinen vorherigen Schnitt, daran kann sich DragKnife nicht orientieren, deshalb richtest du dort das Messer von Hand aus (siehe Hinweis oben).
- **Konturende (Overcut):** Die Spindel führt die Kontur, die Klingenspitze schleppt um den Blade offset hinterher. Ohne Korrektur bliebe die Spitze am Ende deshalb einen Blade offset **vor** dem programmierten Endpunkt stehen. Darum fährt die Spindel am Ende noch einen Blade offset **in Schnittrichtung weiter** (mit Schnitt-Vorschub), bis die **Klingenspitze** den Endpunkt erreicht. Die Spitze schneidet also bis zum Konturende, nicht darüber hinaus. Nur die **Spindel** ragt über das Ende hinaus, dort muss Platz sein. In Pro entfällt dieser separate Move, weil die Spindel mit der Pfad-Kompensierung ohnehin schon vorausläuft.
