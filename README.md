# SlidesTemplate

A Beamer presentation template based on the [Elegant Slides](https://www.overleaf.com/latex/templates/elegant-slides/grfrxqmqkqkj) theme by Lars Spreng, adapted for 16:9 format with simplified structure and Chinese language support.

## Structure

```
beamer/
├── slides.tex            # Main presentation (English)
├── slides_chinese.tex         # Main presentation (Chinese)
├── references.bib        # Bibliography
├── Makefile              # Build system
└── styles/
    ├── beamerthemeelegant.sty  # Theme (colors, fonts, layout)
    ├── loadslides.tex          # Package configuration (English)
    └── loadslides_chinese.tex       # Package configuration (Chinese, XeLaTeX)
```

## Building

Requires a TeX Live installation with `pdflatex`, `xelatex`, and `biber`.

```bash
# English version
make

# Chinese version
make cn

# Remove all build artifacts and output PDFs
make clean
```

Auxiliary files are written to `build/` to keep the working directory clean.

## Color Themes

Set the `style` option in `loadslides.tex` (or `loadslides_chinese.tex`):

```latex
\usepackage[style=red]{styles/beamerthemeelegant}
```

| Style     | Primary | Secondary | Tertiary |
|-----------|---------|-----------|----------|
| `lecture` | Navy    | Dark Red  | Forest   |
| `gold`    | Navy    | Gold      | Crimson  |
| `red`     | Navy    | Pink      | Teal     |
| `orange`  | Navy    | Orange    | Teal     |
| `gray`    | Navy    | Dark Red  | Gray     |

## Chinese Support

`slides_chinese.tex` uses XeLaTeX with `xeCJK`. The Chinese font is set to **SimSun** (宋体). The font must be available to fontconfig — on WSL, copy it from the Windows font directory:

```bash
mkdir -p ~/.local/share/fonts
cp /mnt/c/Windows/Fonts/simsun.ttc ~/.local/share/fonts/
fc-cache -f ~/.local/share/fonts/
```
