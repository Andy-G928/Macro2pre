# Lingnan Beamer Template

This folder packages the LaTeX presentation settings used in the current project
as a reusable Beamer template.

## Compile

Use XeLaTeX:

```powershell
xelatex -interaction=nonstopmode -halt-on-error main.tex
xelatex -interaction=nonstopmode -halt-on-error main.tex
```

You can also use `latexmk` if it is installed:

```powershell
latexmk -xelatex main.tex
```

## What To Edit

- `main.tex`: title, author, institution, section page labels, and section inputs.
- `tex/*.tex`: slide content.
- `image/logo3.png`: footline logo. If you rename or remove it, also update
  `beamerouterthemelingnan.sty`.

## Template Contents

- `beamerthemelingnan.sty`
- `beamercolorthemelingnan.sty`
- `beamerinnerthemelingnan.sty`
- `beamerouterthemelingnan.sty`
- `main.tex`
- `tex/01_introduction.tex`
- `tex/02_core_analysis.tex`
- `tex/99_appendix.tex`
- `image/logo3.png`

The template keeps the original visual system: red and grey color palette,
custom title page, custom section divider pages, compact math/list spacing,
speaker-aware footline, and appendix derivation buttons.
