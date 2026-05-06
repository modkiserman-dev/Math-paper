# Paper Project

This folder contains the LaTeX source for the paper.

## Main Files

- `main.tex`: main LaTeX source
- `build/main.pdf`: compiled PDF output
- `latexmkrc`: build configuration for `latexmk`
- `notes/notation_and_proof_conventions.md`: notation and proof conventions
- `../README.md`: project-level writing guide

## Suggested Folders

- `sections/`: split section files if the paper grows
- `figures/`: figures used by `\includegraphics`
- `tables/`: standalone table files
- `bib/`: bibliography files such as `.bib`
- `notes/`: project direction, notation, and proof-convention notes

## Build

Run this command from this folder:

```powershell
latexmk main.tex
```

Clean generated files:

```powershell
latexmk -C main.tex
```

## Writing Guide

Before making mathematical edits, read:

- `../README.md`
- `notes/notation_and_proof_conventions.md`

These files record the intended notation, especially the convention that
`F(s,y)` denotes the Dirichlet series built from `(1+y)^{omega(n)}` and that
`T_j(x)` is extracted as the coefficient of `y^j` in `A(x,y)`.
