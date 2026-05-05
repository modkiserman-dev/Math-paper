# Paper Project

This folder contains the LaTeX source for the paper.

## Main Files

- `main.tex`: main LaTeX source
- `build/main.pdf`: compiled PDF output
- `latexmkrc`: build configuration for `latexmk`

## Suggested Folders

- `sections/`: split section files if the paper grows
- `figures/`: figures used by `\includegraphics`
- `tables/`: standalone table files
- `bib/`: bibliography files such as `.bib`

## Build

Run this command from this folder:

```powershell
latexmk main.tex
```

Clean generated files:

```powershell
latexmk -C main.tex
```
