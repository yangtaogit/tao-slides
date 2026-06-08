# Tao Slides

This repository contains matching Beamer and PowerPoint slide templates.

- `powerpoint/slides.pptx` is the PowerPoint template. Generated master variants are not maintained.
- `beamer/` is the LaTeX Beamer template rebuilt to match the PowerPoint visual system.
- Both templates use the same minimal visual language: white background, navy titles, a single title rule, sparse bullets, and bottom-right page numbers.
- PowerPoint text fonts are set to **Microsoft YaHei**.
- Beamer uses **Microsoft YaHei** when available, with compile-safe fallbacks.

## Preview

[Open the Chinese Beamer PDF](beamer/slides_chinese.pdf)

![Chinese Beamer preview](docs/slides_chinese_preview.png)

## Slide Spec

- Page size: `33.867 cm x 19.05 cm`.
- Page title: `36 pt`.
- Title rule: `3 pt`.
- Subtitle: `24 pt`.
- Body text: `20 pt`.

## Structure

```text
beamer/
├── slides.tex                 # English Beamer starter
├── slides_chinese.tex         # Chinese Beamer starter
├── Makefile                   # Build system
└── styles/
    ├── beamerthemetao.sty     # Tao Beamer theme
    ├── loadslides.tex         # English package/font setup
    └── loadslides_chinese.tex # Chinese package/font setup

powerpoint/
└── slides.pptx                # PowerPoint template
```

## Building Beamer

The Beamer template builds with XeLaTeX.

```bash
cd beamer
make      # English version
make cn   # Chinese version
make clean
```

## Fonts

For best cross-format consistency, the Chinese Beamer template uses the Windows Microsoft YaHei font directly when it is available at `/mnt/c/Windows/Fonts/msyh.ttc`. You can also install it into fontconfig manually:

```bash
mkdir -p ~/.local/share/fonts
cp /mnt/c/Windows/Fonts/msyh*.ttc ~/.local/share/fonts/
fc-cache -f ~/.local/share/fonts/
```

If Microsoft YaHei is unavailable, the English Beamer template falls back to TeX Gyre Heros, and the Chinese template falls back to SimSun.
