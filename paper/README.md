# Paper Project

This folder contains the LaTeX source for the paper.

## Main Files

- `main.tex`: main LaTeX source
- `sections/*.tex`: section-level source files included by `main.tex`
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

## Section Files

The body of the paper is split as follows:

- `sections/01-introduction.tex`
- `sections/02-proof-of-identity.tex`
- `sections/03-dirichlet-series-factorization.tex`
- `sections/04-perron-contour-deformation.tex`
- `sections/05-local-hankel-analysis.tex`
- `sections/06-extraction-main-theorem.tex`
- `sections/07-outlook.tex`
