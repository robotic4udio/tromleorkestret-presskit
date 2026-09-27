# Tromleorkestret — Booking Sheet

Hand-editable XeLaTeX press/booking one-sheet for Tromleorkestret.

## Files

- `main.tex` — the LaTeX source (2-page A4 booking sheet)
- `img/` — photo assets used by `main.tex` (see `img/README.md` for how each crop was made)
- `Tromleorkestret - Booking Sheet.pdf` — the current compiled PDF

## Building

Requires XeLaTeX with system fonts Lora, Bitstream Charter, and DejaVu Sans Condensed.

```bash
xelatex -interaction=nonstopmode main.tex
xelatex -interaction=nonstopmode main.tex   # run twice for cross-references
```
