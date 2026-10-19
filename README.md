# DragKnife – Anleitung

Quelltexte der Kunden-Anleitung zum Autodesk-Fusion-Add-In **DragKnife** (Eco und Pro).

**Online:** <https://macmanpb.github.io/dragknife-docs/>

Die Seite entsteht mit [MkDocs](https://www.mkdocs.org/) und dem Material-Theme und wird bei jedem
Push auf `main` über GitHub Pages veröffentlicht (`.github/workflows/pages.yml`).

## Lokal ansehen

Einmalig:

```bash
uv venv .venv
uv pip install --python .venv/bin/python -r requirements.txt
```

Dann:

```bash
.venv/bin/mkdocs serve -a 127.0.0.1:8001
```

Fehlerfrei bauen (bricht bei jeder Warnung ab):

```bash
.venv/bin/mkdocs build --strict
```

`mkdocs-glightbox` ist auf `0.4.0` gepinnt: Version `0.5.2` verliert zusammen mit `selectolax 1.0.1`
alle Bilder im erzeugten HTML.

## Bilder

Ablage in `docs/assets/img/`.

- Bilder aus den Add-In-Ansichten (Bibliothek, Kalibrierung, Vorschau) entstehen im Dev-Modus des
  Add-In-Repos (`…?dev&theme=light` bzw. `&theme=dark`) und liegen als Paar `name-light.png` und
  `name-dark.png` vor. Eingebunden werden beide mit `#only-light` und `#only-dark` im Bildverweis.
- Fusion-Screenshots: eine Variante genügt (`fusion-*.png`, `dialog-*.png`, `meldung-*.png`).
- Bildunterschriften (`<figcaption>`) enthalten kein Markdown, Fettdruck dort mit `<strong>`.

## Lizenz

© 2026 Peter Boeker (pbmilltec). Alle Rechte vorbehalten, siehe [LICENSE](LICENSE).
